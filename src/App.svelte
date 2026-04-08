<script>
    import svelteLogo from "./assets/svelte.svg";
    import viteLogo from "./assets/vite.svg";
    import heroImg from "./assets/hero.png";
    import Counter from "./components/Counter.svelte";
    import Header from "./components/Header.svelte";
    import Sb from "./components/Sb.svelte";
    import placeholder from "/placeholder.svg";
    import imagenEmpresa1 from "/imagenEmpresa1.png";
</script>

<Header></Header>
<Sb></Sb>
<section id="center">
    <div class="hero">
        <img src={heroImg} class="base" width="170" height="179" alt="" />
        <img src={svelteLogo} class="framework" alt="Svelte logo" />
        <img src={viteLogo} class="vite" alt="Vite logo" />
    </div>
    <div class="hola">
        <h1>Get started</h1>
        <p>
            Edit <code>src/App.svelte</code> <span>and save to test</span>
            <code>HMR</code>
        </p>
    </div>
    <Counter />
</section>

<section id="vision_section">
    <div class="the_vision">
        <h1>Nuestra Visión</h1>
        <p class="vision">
            Ser la empresa líder en el mercado de remodelaciones y tecnología
            estructural al igual que en el apartado de seguridad cibernética.
        </p>
        <div id="carouselCompany" class="carousel slide" data-ride="carousel">
            <ol class="carousel-indicators">
                <li
                    data-target="#carouselCompany"
                    data-slide-to="0"
                    class="active"
                ></li>
                <li data-target="#carouselCompany" data-slide-to="1"></li>
                <li data-target="#carouselCompany" data-slide-to="2"></li>
            </ol>
            <div class="carousel-inner">
                <div class="carousel-item active">
                    <img
                        id="imgCarouselCompany"
                        class="d-block w-100"
                        src={imagenEmpresa1}
                        alt="First slide"
                    />
                </div>
                <div class="carousel-item">
                    <img
                        id="imgCarouselCompany"
                        class="d-block w-100"
                        src={placeholder}
                        alt="Second slide"
                    />
                </div>
                <div class="carousel-item">
                    <img
                        id="imgCarouselCompany"
                        class="d-block w-100"
                        src={placeholder}
                        alt="Third slide"
                    />
                </div>
            </div>
            <a
                class="carousel-control-prev"
                href="#carouselCompany"
                role="button"
                data-slide="prev"
            >
                <span class="carousel-control-prev-icon" aria-hidden="true"
                ></span>
                <span class="sr-only">Previous</span>
            </a>
            <a
                class="carousel-control-next"
                href="#carouselCompany"
                role="button"
                data-slide="next"
            >
                <span class="carousel-control-next-icon" aria-hidden="true"
                ></span>
                <span class="sr-only">Next</span>
            </a>
        </div>
    </div>
</section>
<div class="ticks"></div>
<section id="next-steps">
    <div id="docs">
        <svg class="icon" role="presentation" aria-hidden="true">
            <use href="/icons.svg#documentation-icon"></use>
        </svg>
        <h2>Documentation</h2>
        <p>Your questions, answered</p>
        <ul>
            <li>
                <a href="https://vite.dev/" target="_blank" rel="noreferrer">
                    <img class="logo" src={viteLogo} alt="" />
                    Explore Vite
                </a>
            </li>
            <li>
                <a href="https://svelte.dev/" target="_blank" rel="noreferrer">
                    <img class="button-icon" src={svelteLogo} alt="" />
                    Learn more
                </a>
            </li>
        </ul>
    </div>
    <div id="social">
        <svg class="icon" role="presentation" aria-hidden="true">
            <use href="/icons.svg#social-icon"></use>
        </svg>
        <h2>Connect with us</h2>
        <p>Join the Vite community</p>
        <ul>
            <li>
                <a
                    href="https://github.com/vitejs/vite"
                    target="_blank"
                    rel="noreferrer"
                >
                    <svg
                        class="button-icon"
                        role="presentation"
                        aria-hidden="true"
                    >
                        <use href="/icons.svg#github-icon"></use>
                    </svg>
                    GitHub
                </a>
            </li>
            <li>
                <a
                    href="https://chat.vite.dev/"
                    target="_blank"
                    rel="noreferrer"
                >
                    <svg
                        class="button-icon"
                        role="presentation"
                        aria-hidden="true"
                    >
                        <use href="/icons.svg#discord-icon"></use>
                    </svg>
                    Discord
                </a>
            </li>
            <li>
                <a
                    href="https://x.com/vite_js"
                    target="_blank"
                    rel="noreferrer"
                >
                    <svg
                        class="button-icon"
                        role="presentation"
                        aria-hidden="true"
                    >
                        <use href="/icons.svg#x-icon"></use>
                    </svg>
                    X.com
                </a>
            </li>
            <li>
                <a
                    href="https://bsky.app/profile/vite.dev"
                    target="_blank"
                    rel="noreferrer"
                >
                    <svg
                        class="button-icon"
                        role="presentation"
                        aria-hidden="true"
                    >
                        <use href="/icons.svg#bluesky-icon"></use>
                    </svg>
                    Bluesky
                </a>
            </li>
        </ul>
    </div>
</section>

<div class="ticks"></div>
<section id="spacer"></section>

<footer></footer>

<style>
    .hola p span {
        color: #424242 !important;
    }
</style>
