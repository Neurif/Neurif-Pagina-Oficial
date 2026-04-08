<script>
    let card;

    let rotateX = $state(0);
    let rotateY = $state(0);

    function HandleMouseMove(e) {
        const rect = card.getBoundingClientRect();

        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;

        // Normaliza (0 → 1)
        const percentX = x / rect.width;
        const percentY = y / rect.height;

        // Convert to -1 → 1
        const tiltX = (percentY - 0.5) * 2;
        const tiltY = (percentX - 0.5) * 2;

        const maxTilt = 10;

        rotateX = -tiltX * maxTilt;
        rotateY = tiltY * maxTilt;
    }

    function HandleMouseLeave() {
        rotateX = 0;
        rotateY = 0;
    }

    // Por fuerza, la variable para aceptar componentes se tiene que llamar children
    let { children, fillParent = false } = $props();
</script>

<div
    class="wrapper"
    role="presentation"
    onmousemove={HandleMouseMove}
    onmouseleave={HandleMouseLeave}
    class:fillParent={fillParent}
>
    <div
        class="card"
        bind:this={card}
        style="transform: rotateX({rotateX}deg) rotateY({rotateY}deg);"
        role="presentation"
        onmousemove={HandleMouseMove}
        onmouseleave={HandleMouseLeave}
        class:fillParent={fillParent}
    >
        {@render children?.()}
    </div>
</div>

<style>
    .fillParent
    {
        width: 100%;
        height: 100%;
    }

    .wrapper {
        perspective: 800px;
    }

    .card {
        border-radius: 2em;
        background-color: var(--card-bg);
        transition: transform 0.2s ease;
        will-change: transform;
        padding: 16px;
        box-sizing: border-box;
    }
</style>
