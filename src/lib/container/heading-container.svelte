<div class="heading-container">
    <slot name="heading" >
        <h1 id={id}>{heading}</h1>
    </slot>
    <slot/>
</div>

<style>
    .heading-container {
        margin: 1rem auto;
        width: var(--default-width);
        max-width: var(--default-max-width);
        height: auto;
    }

    .heading-container h1 {
        padding: 1rem 0;
        font-weight: 500;
        font-size: 2rem;
        color: var(--accent-color);
        font-stretch: expanded;
        scroll-margin: var(--navbar-height);
    }

    @media screen and (max-width: 500px) {
        .heading-container h1 {
            font-size: 1.6rem;
        }
    }
</style>

<script>
    export let heading
    export let id = ""
</script>