<script>
    import Card from "./3DCard.svelte";
    import Brain from "@lucide/svelte/icons/brain-circuit";
    import Building from "@lucide/svelte/icons/building";
    import Plan from "@lucide/svelte/icons/drafting-compass";
    import Time from "@lucide/svelte/icons/calendar-clock";
    import "../icons.css";
</script>

<div class="wrapper">
    <h1>
        Sobre Nosostros
    </h1>
    <div class="grid">
        <Card fillParent>
            <div class="cardContent">                
                <Brain class="about-us-icon"/>
                <p>
                    NeurIf es una empresa que moderniza la construcción y remodelación mediante inteligencia artificial.
                </p>
            </div>
        </Card>
        <Card fillParent>
            <div class="cardContent">
                <Building class="about-us-icon"/>
                <p>
                    Integramos el diseño estructural, la seguridad cibernética en IoT y el bienestar de los usuarios en cada proyecto.
                </p>
            </div>
        </Card>
        <Card fillParent>
            <div class="cardContent">
                <Plan class="about-us-icon"/>
                <p>
                    Nuestra IA permite planificar y ejecutar proyectos con recomendaciones estratégicas basadas en ubicación, cimientos y espacio disponible.
                </p>
            </div>
        </Card>
        <Card fillParent>
            <div class="cardContent">
                <Time class="about-us-icon"/>
                <p>
                    Reducimos costos y tiempo al automatizar la búsqueda de proveedores e inmuebles, aumentando la eficiencia de forma innovadora y accesible.
                </p>
            </div>
        </Card>
    </div>
</div>
<style>
    .wrapper
    {
        margin: 32px 15%;
    }

    .grid
    {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        grid-auto-rows: 300px;
        gap: 32px;
    }

    .cardContent
    {
        display: flex;
        flex-direction: column;
        width: 100%;
        height: 100%;
    }

    .cardContent p
    {
        margin-top: auto;
    }
</style>