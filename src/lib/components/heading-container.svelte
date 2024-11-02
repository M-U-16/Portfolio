<div class="heading-container">
    <h1>&lt;{heading}&gt;</h1>
    <slot/>
    <h1>&lt;&#47;{heading}&gt;</h1>
</div>

<style>
    .heading-container {
        width: 90%;
        margin: auto;
    }

    .heading-container h1 {
        color: var(--accent-color);
        padding: 0.5rem;
        font-size: 1.5rem;
        font-weight: 500;
    }
</style>

<script>
    export let heading
</script>