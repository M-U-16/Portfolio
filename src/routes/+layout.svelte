<svelte:head>
    <title>maurice-ueberfeld.de</title>
</svelte:head>

<Navbar />
<slot></slot>

<script>
    import {page} from "$app/stores"
    import { onNavigate } from "$app/navigation"
    import Navbar from "$lib/components/Navbar.svelte";
    import ReactiveNavbar from "$lib/components/ReactiveNavbar.svelte";
    
    onNavigate((nav)=> {

        /* if (nav.to.route.id == "/") */
        if ($page.url.pathname == nav.to.route.id) {
            return
        }

        if (!document.startViewTransition) return
        return new Promise((res)=>{
            document.startViewTransition(async()=>{
                res()
                await nav.complete
            })
        })
    })
</script>