<script>
    import { onMount } from "svelte";
    let misionRef;
    let misionProgress = 0;
    let speedMultiplier = 2;

    function updateMisionProgress() {
        if (!misionRef) return;
        const rect = misionRef.getBoundingClientRect();
        const windowHeight =
            window.innerHeight || document.documentElement.clientHeight;
        const progress = 1 - rect.top / windowHeight;
        misionProgress = Math.min(Math.max(progress, 0), 1);
    }

    onMount(() => {
        updateMisionProgress();
        window.addEventListener("scroll", updateMisionProgress, {
            passive: true,
        });
        window.addEventListener("resize", updateMisionProgress);
        return () => {
            window.removeEventListener("scroll", updateMisionProgress);
            window.removeEventListener("resize", updateMisionProgress);
        };
    });

    import placeholder from "/placeholder.svg";
    import imagenEmpresa1 from "/imagenEmpresa1.png";
    import "bootstrap/dist/css/bootstrap.min.css";
    import "bootstrap/dist/js/bootstrap.bundle.min.js";
</script>

<div
    class="la_vision"
    bind:this={misionRef}
    style="opacity: {Math.min(misionProgress * speedMultiplier, 1)}; transform: translateY({30 -
        misionProgress * 30}px); visibility: {misionProgress > 0
        ? 'visible' 
        : 'hidden'};"
>
    <h1>Nuestra Misión</h1>
    <p style="max-width: 1000px; margin: 0 auto;">
        Buscamos brindar una IA que ayude a los usuarios a idear y ejecutar mejor la remodelación 
        y construcción de infraestructuras. Nuestra empresa busca generar de manera estructurada la proyección de las ideas de remodelación, ajustando cada proyecto de acuerdo con la seguridad estructural y cibernética, 
        así como con la estabilidad mental y física de quien o quienes planteen la propuesta.
    </p>
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
