<script>
    import logo from '/logo.png'
</script>

<header>
<div class="Header">
    <div class="logo-header">
        <img src={logo} alt="logo" style="width: 100px; height: 100px;"/>
    </div>

    <div class="search-container">
        <div class="search-part">
            <input type="search" placeholder="Search..." class="search-input"/>
            <button type="submit" class="search-button">🔍</button>
        </div>
    </div>

    <div class="barra-navegacion-header">
        <a href="mision">Misión</a>
        <a href="vision">Visión</a>
        <a href="sobre-nosotros">Sobre Nosotros</a>
    </div>
</div>
</header>

<style>
header {
    position: sticky;
    top: 0;
    z-index: 100;
}

.Header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background-color: #f8f8f8;
}

.logo-header {
    flex: 1;
}

.search-container {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
}

.search-part {
    display: flex;
    align-items: center;
    border: 1.5px solid #ccc;
    border-radius: 25px;
    overflow: hidden;
    transition: border-color 0.2s;
}

.search-part:focus-within {
    border-color: #2196F3;
}

.search-input {
    border: none;
    padding: 8px 14px;
    outline: none;
    font-size: 15px;
    width: 220px;
    background: transparent;
}

.search-button {
    background: none;
    border: none;
    padding: 8px 12px;
    cursor: pointer;
    font-size: 16px;
}

.barra-navegacion-header {
    flex: 1;
    display: flex;
    justify-content: flex-end;
}

.barra-navegacion-header a {
    margin: 0 1rem;
    text-decoration: none;
    color: #333;
    font-weight: bold;
    cursor: pointer;
}


</style>