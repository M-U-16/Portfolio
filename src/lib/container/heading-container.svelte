<div class="heading-container">
    <h1>{heading}</h1>
    <slot/>
</div>

<style>
    .heading-container {
        margin: 1rem auto;
        width: var(--default-width);
        max-width: var(--default-max-width);
    }

    .heading-container h1 {
        padding: 1rem 0;
        font-weight: 500;
        font-size: 2rem;
        color: var(--accent-color);
        font-stretch: expanded;
    }
</style>

<script>
    export let heading
</script>