<svelte:window bind:scrollY={y}/>

<div class="container">
<div
    class="wrapper"
    style={navbarTop}
    class:sticky={navbarSticky}
    bind:offsetHeight={navbarHeight}
>
    <div class="navbar">
        <!-- <div class="container flex-center"> -->
            <a class="logo" href="/">
                <h1>
                    <span>Maurice</span>
                    <span>Ueberfeld</span>
                </h1>
            </a>
            <nav>
                <a
                    class="link"
                    class:active={current=="/about_me"}
                    href="/about_me"
                >Über mich</a>
                <a
                    class="link"
                    class:active={current=="/projekte"}
                    href="/projekte"
                >Projekte</a>
            </nav>
        <!-- </div> -->
    </div>
</div>
</div>

<script>
    let y, last_y = 0
    let navbarHidden = false
    let navbarTop, navbarActive
    let navbarHeight, navbarSticky

    import {page} from "$app/stores"
    let current
    $: current = $page.url.pathname
    
    $: (() => {
        if (
            navbarActive &&
            y <= navbarHeight &&
            y < last_y &&
            y != 0
        ) {
            return
        } else {
            navbarActive = false
        }
        
        if (navbarSticky) {
            navbarSticky = false
        }

        if (y <= navbarHeight) {
            navbarTop = `top: ${-y}px;`
            navbarHidden = false
            last_y = y;
            return
        } else if (!navbarHidden) {
            navbarTop = `top: ${-navbarHeight}px;`
            navbarHidden = true
            last_y = y
            return
        }

        navbarSticky = true

        if (y < last_y) {
            navbarActive = true
        } else {
            navbarActive = false
        }

        if (navbarActive) {
            navbarTop = `top:0px;`
        } else {
            navbarTop = `top:${(-navbarHeight).toString()}px`
        }

        last_y = y
    })()
</script>

<style>
    .container {
        width: 100%;
        height: var(--navbar-height);
    }

    .wrapper {
        top: 0;
        width: 100vw;
        position: fixed;
        height: var(--navbar-height);
    }

    .wrapper.sticky {
        transition: 0.4s ease;
    }

    .navbar {
        --shadow-gradient: 180deg, rgba(194, 194, 194, 0.21), transparent;

        display: flex;
        position: absolute;
        width: 100%;
        align-items: center;
        opacity: 1 !important;
        z-index: 1000;
        background-color: red;
        view-transition-name: navbar;
        height: var(--navbar-height);
        justify-content: space-between;
        box-shadow: var(--default-box-shadow);
    }

    /* .navbar::after {
        height: 0;
        top: 100%;
        width: 100%;
        content: "";
        position: absolute;
        transition: 0.2s ease;
    } */

    .navbar nav {
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
</style>