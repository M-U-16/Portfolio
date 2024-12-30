<div class="project">
    <video autoplay loop muted playsinline>
        <source src={src} type={type}>
        <track kind="captions" />
    </video>
    <div class="project-info">
        
        <slot name="head"/>
        <div class="description">
            <slot name="description"/>
        </div>
        <div class="techs">
            <slot name="techs" />
        </div>
        <div class="links">
            {#if liveProject != ""}
                <a
                href={liveProject}
                target="_blank"
                class="live-site"
                >
                    <Open />
                    <slot name="live-link">
                        <span>Live Seite</span>
                    </slot>
                </a>
            {/if}
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
    import Github from "$lib/icons/dev/Github.svelte"
    import Open from "$lib/icons/Open.svelte"

    export let src
    export let type
    export let projectLink
    export let liveProject = ""
</script>

<style>
    .project {
        display: grid;
        grid-template-columns: subgrid;
        grid-template-rows: auto 1fr;

        width: 100%;
        box-shadow: 0px 0px 3px rgb(202, 202, 202);
        border-radius: 5px;
        background-color: white;
        overflow: hidden;
    }

    .project video {
       width: 100%;
       max-height: min-content;
    }

    /* .project .image-container {
        height: 190px;
        width: 100%;
        overflow: hidden;
    } 
    .project .imgage-container img {
        height: 100%;
    } */

    .project-info {
        display: grid;
        grid-template-rows: auto 1fr auto;
        
        padding: 0.5rem 1rem 1rem 1rem;
    }

    .description {
        margin-bottom: 1rem;
        font-size: 1.2rem;
        width: 100%;
    }

    .project .techs {
        font-size: 0.8rem;
        padding: 0.5rem 0;
    }

    .links {
        gap: 1rem;
        height: 100%;
        display: flex;
    }
    
    .github-repo,
    .live-site {
        flex: 1;
        display: flex;
        align-items: center;
        text-decoration: none;
        width: 50%;
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

    @media screen and (max-width: 400px) {
        .links {
            flex-direction: column;
            gap: 0.25rem;
        }

        .links a {
            width: 100%;
        }
    }

    @media screen and (max-width: 380px) {
        .project {
            border-radius: 0;
        }
    }
</style>