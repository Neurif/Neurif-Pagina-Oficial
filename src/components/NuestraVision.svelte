<script>
    import { onMount } from "svelte";
    import { fade } from "svelte/transition";

    import placeholder from "/placeholder.svg";
    import imagenEmpresa1 from "/imagenEmpresa1.png";

    let visionRef;
    let visionProgress = 0;

    function updateVisionProgress() {
        if (!visionRef) return;
        const rect = visionRef.getBoundingClientRect();
        const windowHeight =
            window.innerHeight || document.documentElement.clientHeight;
        const progress = 1 - rect.top / windowHeight;
        visionProgress = Math.min(Math.max(progress, 0), 1);
    }

    onMount(() => {
        updateVisionProgress();
        window.addEventListener("scroll", updateVisionProgress, {
            passive: true,
        });
        window.addEventListener("resize", updateVisionProgress);
        return () => {
            window.removeEventListener("scroll", updateVisionProgress);
            window.removeEventListener("resize", updateVisionProgress);
        };
    });

    const slides = [
        { src: imagenEmpresa1, alt: "Slide 1" },
        { src: placeholder, alt: "Slide 2" },
        { src: placeholder, alt: "Slide 3" },
    ];

    let current = 0;

    function prev() {
        current = (current - 1 + slides.length) % slides.length;
    }

    function next() {
        current = (current + 1) % slides.length;
    }

    function goTo(i) {
        current = i;
    }
</script>

<div
    class="la_vision"
    bind:this={visionRef}
    style="opacity: {visionProgress}; transform: translateY({30 -
        visionProgress * 30}px); visibility: {visionProgress > 0
        ? 'visible'
        : 'hidden'};"
>
    <h1>Nuestra Visión</h1>
    <p>
        Ser la empresa líder en el mercado de remodelaciones y tecnología
        estructural al igual que en el apartado de seguridad cibernética.
    </p>

    <div class="carousel">
        <div class="carousel-track">
            {#key current}
                <img
                    src={slides[current].src}
                    alt={slides[current].alt}
                    transition:fade={{ duration: 1000 }}
                />
            {/key}
        </div>

        <button class="arrow arrow-prev" on:click={prev} aria-label="Anterior">
            &#8249;
        </button>
        <button class="arrow arrow-next" on:click={next} aria-label="Siguiente">
            &#8250;
        </button>

        <div class="indicators">
            {#each slides as _, i}
                <button
                    class="dot"
                    class:active={i === current}
                    on:click={() => goTo(i)}
                    aria-label="Slide {i + 1}"
                ></button>
            {/each}
        </div>
    </div>
</div>

<style>
    .la_vision {
        opacity: 0;
        visibility: hidden;
        transform: translateY(30px);
        transition:
            opacity 0.2s ease,
            transform 0.2s ease;
    }

    .carousel {
        position: relative;
        width: 100%;
        max-width: 1000px;
        margin: 10px auto;
        overflow: hidden;
        border-radius: 8px;
        aspect-ratio: 16 / 9;
        background: #000;
    }

    .carousel-track {
        width: 100%;
        height: 100%;
        position: relative;
    }

    .carousel-track img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        position: absolute;
        top: 0;
        left: 0;
    }

    .arrow {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        background: rgba(0, 0, 0, 0.4);
        color: white;
        border: none;
        font-size: 48px;
        line-height: 1;
        padding: 8px 16px;
        cursor: pointer;
        border-radius: 4px;
        transition: background 0.2s;
        z-index: 10;
    }

    .arrow:hover {
        background: rgba(0, 0, 0, 0.7);
    }

    .arrow-prev {
        left: 12px;
    }
    .arrow-next {
        right: 12px;
    }

    .indicators {
        position: absolute;
        bottom: 12px;
        left: 50%;
        transform: translateX(-50%);
        display: flex;
        gap: 8px;
        z-index: 10;
    }

    .dot {
        width: 40px;
        height: 4px;
        border: none;
        background: rgba(255, 255, 255, 0.5);
        cursor: pointer;
        padding: 0;
        transition: background 0.2s;
    }

    .dot.active {
        background: white;
    }
</style>
