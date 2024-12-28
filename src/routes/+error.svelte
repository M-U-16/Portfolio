<div class="error-page">
    <Warning />
    <h1>404 Not Found</h1>
    <a href="/">&lt; Zur Startseite</a> 
</div>

<style>
    div {
        color: #ff2929;
        width: 100%;
        padding-top: 5rem;
        height: calc(100% - var(--navbar-height));

        display: flex;
        align-items: center;
        flex-direction: column;
    }

    h1 {
        color: #ff2929;
    }
    
    :global(.error-page .icon) {
        width: 3rem;
        height: 3rem;
    }

    a {
        color: var(--accent-color);
        text-decoration: none;
    }
</style>

<script>
    import Warning from "$lib/icons/Warning.svelte";
</script>