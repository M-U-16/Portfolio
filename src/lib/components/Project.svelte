<div class="project">
    <video autoplay loop muted playsinline>
        <source src={src} type="video/webm">
        <track kind="captions" />
    </video>
    <div class="project-info">
        <slot name="head"/>
        <div class="description">
            <slot/>
        </div>
        <div class="links">
            <a
            href={liveProject}
            target="_blank"
            class="live-site"
            >
                <Open />
                <span>Live Seite</span>
            </a>
            <a
                href={projectLink}
                target="_blank"
                class="github-repo"
            >
                <Github />
                <span>Github Repo</span>
            </a>
        </div>
    </div>
</div>

<script>
    import Github from "$lib/icons/Github.svelte"
    import Open from "$lib/icons/Open.svelte"

    export let src
    export let projectLink
    export let liveProject
</script>

<style>
    .project {
        width: 100%;
        box-shadow: 0px 0px 3px rgb(202, 202, 202);
        border-radius: 5px;
        overflow: hidden;
        display: flex;
        max-width: 400px;
        flex-direction: column;
        background-color: white;
    }

    .project video {
        max-width: 600px;
        width: 100%;
    }

    .project-info {
        padding: 1rem;
    }

    .links {
        display: flex;
        gap: 1rem;
    }
    
    .github-repo,
    .live-site {
        flex: 1;
        display: flex;
        align-items: center;
        text-decoration: none;
        width: 10rem;
        justify-content: center;
        padding: 0.5rem;
        border-radius: 5px;
        gap: 0.5rem;
        color: white;
        font-size: 1.1rem;
        transition: 0.3s ease;
    }

    .live-site {
        background-color: var(--accent-color);
        border: 1px solid var(--accent-color);
    }

    .github-repo {
        color: white;
        background-color: black;
        border: 1px solid black;
    }

    :global(.github-repo .icon, .live-site .icon) {
        width: 1.5rem;
        height: 1.5rem;
    }

    .live-site:hover {
        background-color: transparent;
        color: var(--accent-color);
    }

    .github-repo:hover {
        background-color: transparent;
        color: black;
    }
</style>