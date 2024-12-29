<PageContainer>
    <footer>
        <Contact />
    </footer>
</PageContainer>

<script>
    import PageContainer from "$lib/container/page-container.svelte";
    import Contact from "$lib/components/Contact.svelte";
</script>

<style>
    footer {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        border-radius: 5px 5px 0 0;
        background-color: white;
        box-shadow: var(--default-box-shadow);
    }

    :global(footer .contact .icon) {
        width: 1.5rem;
        height: 1.5rem;
    }

</style>