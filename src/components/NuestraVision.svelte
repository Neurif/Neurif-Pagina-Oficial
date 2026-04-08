<script>
    import { onMount } from "svelte";
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
<<<<<<< HEAD
})
=======

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

    import placeholder from "/placeholder.svg";
    import imagenEmpresa1 from "/imagenEmpresa1.png";
    import "bootstrap/dist/css/bootstrap.min.css";
    import "bootstrap/dist/js/bootstrap.bundle.min.js";
>>>>>>> e7c3f6d4e6b5268f6a664bd069cf2035050961f5
</script>

<div
    class="la_vision"
    bind:this={visionRef}
    style="opacity: {visionProgress}; transform: translateY({30 -
        visionProgress * 30}px); visibility: {visionProgress > 0
        ? 'visible'
        : 'hidden'};"
>
<<<<<<< HEAD
  <h1>Nuestra Visión</h1>
  <p>Ser la empresa líder en el mercado de remodelaciones y tecnología estructural 
    al igual que en el apartado de seguridad cibernética. </p>
</div>
=======
    <h1>Nuestra Visión</h1>
    <p>
        Ser la empresa líder en el mercado de remodelaciones y tecnología
        estructural al igual que en el apartado de seguridad cibernética.
    </p>
    <div id="companyCarousel" class="carousel slide">
        <div class="carousel-indicators">
            <button
                type="button"
                data-bs-target="#companyCarousel"
                data-bs-slide-to="0"
                class="active"
                aria-current="true"
                aria-label="Slide 1"
            ></button>
            <button
                type="button"
                data-bs-target="#companyCarousel"
                data-bs-slide-to="1"
                aria-label="Slide 2"
            ></button>
            <button
                type="button"
                data-bs-target="#companyCarousel"
                data-bs-slide-to="2"
                aria-label="Slide 3"
            ></button>
        </div>
        <div class="carousel-inner">
            <div class="carousel-item active">
                <img src={imagenEmpresa1} class="d-block w-100" alt="slide 1" />
            </div>
            <div class="carousel-item">
                <img src={placeholder} class="d-block w-100" alt="slide 2" />
            </div>
            <div class="carousel-item">
                <img src={placeholder} class="d-block w-100" alt="slide 3" />
            </div>
        </div>
        <button
            class="carousel-control-prev"
            type="button"
            data-bs-target="#companyCarousel"
            data-bs-slide="prev"
        >
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
        </button>
        <button
            class="carousel-control-next"
            type="button"
            data-bs-target="#companyCarousel"
            data-bs-slide="next"
        >
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
        </button>
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
</style>
>>>>>>> e7c3f6d4e6b5268f6a664bd069cf2035050961f5
