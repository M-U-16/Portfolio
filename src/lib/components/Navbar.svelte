<div class="navbar-container">
<div class="navbar">
    <a class="logo" href="/" class:active={current == "/"}>
        <h1>
            <span>Maurice</span>
            <span>Ueberfeld</span>
        </h1>
    </a>
    <div class="menu">
        <MenuButton toggleMenu={toggleMenu} active={navActive} />
        <nav class:active={navActive}>
            <a
                class="link"
                class:active={current =="/#about_me"}
                href="/#about_me"
                on:click={() => navActive=false}
            >Über mich</a>
            <a
                class="link"
                class:active={current =="/#projekte"}
                href="/#projekte"
                on:click={() => navActive=false}
            >Projekte</a>
        </nav>
    </div>
</div>
</div>

<script>
    import {page} from "$app/stores"
    import MenuButton from "$lib/components/MenuButton.svelte"
    
    let navActive = false

    function toggleMenu() {
        navActive = !navActive
    }

    let current
    $: current = $page.url.pathname + $page.url.hash
</script>

<style>
.navbar-container {
    width: 100%;
    height: var(--navbar-height);
}

.navbar {
    --shadow-gradient: 180deg, rgba(194, 194, 194, 0.21), transparent;
    
    width: 100%;
    height: var(--navbar-height);
    z-index: 1000;
    display: flex;
    position: fixed;
    align-items: center;
    background-color: white;
    justify-content: space-between;
    view-transition-name: navbar;
    box-shadow: var(--default-box-shadow);
}

.navbar .menu {
    display: flex;
    justify-content: center;
    height: 100%;
    position: relative;
    align-items: center;
    view-transition-name: disabled;
}

.navbar .menu nav {
    display: flex;
    align-items: center;
}

.navbar nav .link {
    color: black;
    font-size: 1.2rem;
    position: relative;
    text-decoration: none;
    margin: 0.5rem 0.8rem;
}

.navbar nav .link:last-child {
    margin-right: 2rem;
}

.navbar nav .link::after {
    z-index: 2;
    width: 2px;
    opacity: 0;
    content: "";
    left: 100%;
    height: 85%;
    position: absolute;
    top: calc(50% + 5px);
    transition: 0.3s ease;
    background-color: #3939ff;
    transform: skewX(-15deg)  translateY(-50%) translateX(2px);
}

.navbar nav a.active::after,
.navbar nav a:hover::after {
    top: 50%;
    opacity: 1;
}

.navbar nav a.active,
.navbar nav a:hover {
    color: rgb(57, 57, 255);
}

.logo {
    height: 3rem;
    cursor: pointer;
    margin-left: 1rem;
    display: flex;
    align-items: center;
    text-decoration: none;
    transform: translateX(5px);
    color: black;
    color: var(--accent-color);
}

.logo::after {
    z-index: 2;
    width: 2px;
    opacity: 0;
    content: "";
    left: 100%;
    height: 50%;
    position: absolute;
    top: calc(50% + 5px);
    transition: 0.3s ease;
    background-color: rgb(57, 57, 255);
    transform: rotate(20deg) translateY(-55%);
}

.logo.active::after,
.logo:hover::after {
    opacity: 1;
    top: 50%;
}

.logo h1 {
    display: flex;
    gap: 0.5rem;
    font-family: monospace;
    font-size: 1.2rem;
}

@media screen and (max-width: 500px) {
    .navbar .menu {
        width: 3rem;
    }

    .navbar nav {
        opacity: 0;
        pointer-events: none;
        position: absolute !important;
        top: 100%;
        right: 0;

        padding: 1rem;
        width: 50vw;

        flex-direction: column;
        align-items: start !important;
        box-shadow: var(--default-box-shadow), 0px 0px 5px rgb(190, 190, 190);
        overflow: hidden;
        background-color: white;
        transform: translateY(20px);
        border-radius: 5px;

        transition:
            opacity 0.2s ease,
            transform 0.3s ease;
    }
    
    .navbar nav.active {
        opacity: 1;
        pointer-events: all;
        transform: translateY(10px) translateX(-10px);
    }

    .navbar nav .link {
        font-size: 1.5rem;
        margin: 0;
    }
    
    .navbar nav a:nth-child(2) {
        margin-top: 0.5rem;
    }
    
    .navbar nav .link::after {
        height: 80%;
    }
}

</style>