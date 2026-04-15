<script>
    import svelteLogo from './assets/svelte.svg'
    import viteLogo from './assets/vite.svg'
    import heroImg from './assets/hero.png'
    import Counter from './components/Counter.svelte'
    import Header from './components/Header.svelte';
    import SobreNosotros from './components/SobreNosotros.svelte';
    import Footer from './components/Footer.svelte';
    import NuestraVision from "./components/NuestraVision.svelte";
    import NuestraMision from "./components/NuestraMision.svelte";
</script>

<Header/>

<SobreNosotros/>

<div class="ticks"></div>
<section id="spacer"></section>

<section id="vision">
    <NuestraVision />
</section>

<section id="mision">
    <NuestraMision />
</section>

<Footer></Footer>
