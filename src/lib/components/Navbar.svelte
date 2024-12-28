<div class="navbar-container">
<div class="navbar">
    <a class="logo" href="/" class:active={current == "/"}>
        <h1>
            <span>Maurice</span>
            <span>Ueberfeld</span>
        </h1>
    </a>
    <div class="menu">
        <MenuButton toggleMenu={toggleMenu} />
        <nav class:active={navActive}>
            <a
                class="link"
                class:active={current+currentHash =="/#about_me"}
                href="/#about_me"
            >Über mich</a>
            <a
                class="link"
                class:active={current=="/projekte"}
                href="/projekte"
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

    let current, currentHash
    $: currentHash = $page.url.hash
    $: current = $page.url.pathname
</script>

<style>
.navbar-container {
    height: var(--navbar-height);
    width: 100%;
}

.navbar {
    --shadow-gradient: 180deg, rgba(194, 194, 194, 0.21), transparent;
    width: 100%;
    display: flex;
    position: fixed;
    z-index: 99999;
    align-items: center;
    background-color: white;
    view-transition-name: navbar;
    height: var(--navbar-height);
    justify-content: space-between;
    box-shadow: var(--default-box-shadow);
}

.navbar .menu {
    display: flex;
    height: 100%;
    position: relative;
    align-items: center;
}

.navbar nav {
    display: flex;
    align-items: center;
    
}

/* .navbar nav::before {
    width: 100vw;
    position: absolute;
    content: "";
    right: 0;
    height: 10rem;
    background-color: rgb(255, 255, 255);
    opacity: 0;
    pointer-events: none;
} */

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
    .navbar nav {
        opacity: 0;
        pointer-events: none;
        position: absolute;
        top: 100%;
        right: 0;
        width: 10rem;
        align-items: start;
        flex-direction: column;
        box-shadow: var(--default-box-shadow);
    }

    .navbar nav::before {
        opacity: 1;
    }

    .navbar nav.active {
        opacity: 1;
        pointer-events: all;
    }

    .navbar nav .link {
        font-size: 1.5rem;
    }
}

</style>