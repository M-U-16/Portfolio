<HeadingContainer heading="Skills">
    <div class="skills-container">
        <div class="frontend">
            <h2>Frontend</h2>
            <div class="skills">
                <a
                    class="skill"
                    title="Was ist Html?"
                    href="https://de.wikipedia.org/wiki/Hypertext_Markup_Language"
                    target="_blank"
                >
                    <Html/>
                    <h3>Html</h3>
                </a>
                <a
                    class="skill"
                    title="Was ist Css?"
                    href="https://de.wikipedia.org/wiki/Cascading_Style_Sheets"
                    target="_blank"  
                >
                    <Css/>
                    <h3>CSS</h3>
                </a>
                <a
                    class="skill"
                    title="Was ist Javascript?"
                    href="https://de.wikipedia.org/wiki/JavaScript"
                    target="_blank"
                >
                    <Javascript />
                    <h3>Javascript</h3>
                </a>
                <a
                    class="skill"
                    title="Was ist React?"
                    href="https://react.dev/"
                    target="_blank"
                >
                    <React />
                    <h3>React</h3>
                </a>
                <a
                    class="skill"
                    title="Was ist Svelte?"
                    href="https://svelte.dev"
                    target="_blank"
                >
                    <Svelte />
                    <h3>Svelte</h3>
                </a>
            </div>
        </div>
        <div class="backend">
            <h2>Backend</h2>
            <div class="skills">
                <a
                    class="skill"
                    title="Was ist Python?"
                    href="https://www.python.org"
                    target="_blank"
                >
                    <Python />
                    <h3>Python</h3>
                </a>
                <a
                    class="skill"
                    title="Was ist Go?"
                    href="https://go.dev"
                    target="_blank"
                >
                    <Go />
                    <h3>Go</h3>
                </a>
                <a
                    class="skill"
                    title="Was ist C?"
                    href="https://en.wikipedia.org/wiki/C_(programming_language)"
                    target="_blank"
                >
                    <C />
                    <h3>C</h3>
                </a>
                <a
                    class="skill"
                    title="Was ist Node.js"
                    href="https://nodejs.org/en"
                    target="_blank"
                >
                    <NodeJs />
                    <h3>Node.js</h3>
                </a>
                <a
                    class="skill"
                    title="Was ist ExpressJS?"
                    href="https://expressjs.com"
                    target="_blank"
                >
                    <Express />
                    <h3>ExpressJS</h3>
                </a>
                <a
                    class="skill"
                    title="Was ist Flask?"
                    href="https://de.wikipedia.org/wiki/Flask"
                    target="_blank"
                >
                    <Flask />
                    <h3>Flask</h3>
                </a>
                <a
                    class="skill"
                    title="Was ist Nginx?"
                    href="https://nginx.org/en"
                    target="_blank"
                >
                    <Nginx />
                    <h3>Nginx</h3>
                </a>
            </div>
        </div>
        <div class="last-container">
            <div class="database">
                <h2>Datenbanken</h2>
                <div class="skills">
                    <a
                        class="skill"
                        title="Was ist Sqlite?"
                        href="https://www.sqlite.org/index.html"
                        target="_blank"
                    >
                        <Sqlite />
                        <h3>Sqlite</h3>
                    </a>
                    <a
                        class="skill"
                        title="Was ist MySQL?"
                        href="https://www.mysql.com/de/"
                        target="_blank"
                    >
                        <MySql />
                        <h3>MySQL</h3>
                    </a>
                </div>
            </div>
            <div class="andere">
                <h2>Andere</h2>
                <div class="skills">
                    <a
                        class="skill"
                        title="Was ist Linux?"
                        href="https://de.wikipedia.org/wiki/Linux"
                        target="_blank"
                    >
                        <img alt="Linux Pinguin" src={Linux}/>
                        <h3>Linux</h3>
                    </a>
                    <a
                        class="skill"
                        title="Was ist Git?"
                        href="https://git-scm.com"
                        target="_blank"
                    >
                        <Git />
                        <h3>Git</h3>
                    </a>
                </div>
            </div>
        </div>
    </div>
</HeadingContainer>

<style>
    .skills-container {
        overflow: hidden;
        height: min-content;
    }

    :global(.skill img),
    :global(.skill .icon svg) {
        width: 2rem;
    }

    .skills {
        display: flex;
        gap: 0.5rem;
        flex-wrap: wrap;
    }
    
    .skills .skill {
        padding: 1rem;
        color: black;
        width: 6rem;
        display: flex;
        font-size: 1rem;
        flex-direction: column;
        align-items: center;
        border-radius: 5px;
        text-decoration: none;
        background-color: white;
        box-shadow: inset 0px 0px 2px rgb(181, 181, 181);
    }

    .skills .skill h3 {
        text-align: center;
    }

    .skills .skill:hover {
        color: var(--accent-color, blue);
        text-decoration: underline !important;
    }

    .last-container {
        display: flex;
        gap: 2rem;
        align-items: center;
        grid-template-columns: 1fr 1fr;
    }

    .skills-container > div:nth-child(2),
    .skills-container > div:nth-child(3) {
        margin-top: 1rem;
    }

    @media screen and (max-width: 500px) {
        .last-container {
            gap: 0;
            align-items: start;
            flex-direction: column;
        }

        .last-container .andere {
            margin-top: 1rem;
        }

        .skills .skill {
            width: auto;
            align-items: center;
            gap: 0.5rem;
            flex-direction: row;
        }

        :global(.skill img),
        :global(.skill .icon svg) {
            width: 1.5rem;
        }
    }
</style>

<script>
    import Flask from "$lib/icons/dev/Flask.svelte"
    import MySql from "$lib/icons/dev/MySql.svelte"
    import Sqlite from "$lib/icons/dev/Sqlite.svelte"
    import C from "$lib/icons/dev/C.svelte"
    import NodeJs from "$lib/icons/dev/NodeJs.svelte"
    import Express from "$lib/icons/dev/Express.svelte"
    import Go from "$lib/icons/dev/Go.svelte"
    import Python from "$lib/icons/dev/Python.svelte"
    import Javascript from "$lib/icons/dev/Javascript.svelte"
    import Svelte from "$lib/icons/dev/Svelte.svelte"
    import React from "$lib/icons/dev/React.svelte"
    import Css from "$lib/icons/dev/Css.svelte"
    import Html from "$lib/icons/dev/Html.svelte"
    import Git from "$lib/icons/dev/Git.svelte"
    import Nginx from "$lib/icons/dev/Nginx.svelte"
    import Linux from "$lib/assets/linux.svg"
    
    import HeadingContainer from "$lib/container/heading-container.svelte";
</script>