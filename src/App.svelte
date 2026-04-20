<script>
    import Header from './components/Header.svelte';
    import SobreNosotros from './components/SobreNosotros.svelte';
    import Footer from './components/Footer.svelte';
    import NuestraVision from "./components/NuestraVision.svelte";
    import NuestraMision from "./components/NuestraMision.svelte";
</script>

<Header/>

<SobreNosotros/>

<div class="spacer"></div>

<section id="vision">
    <NuestraVision />
</section>

<div class="spacer"></div>

<section id="mision" style="margin-bottom: 60px;">
    <NuestraMision />
</section>

<div class="spacer"></div>
<div style="height: 300px;"></div>

<Footer></Footer>
