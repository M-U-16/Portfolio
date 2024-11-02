<Header />
<HeadingContainer heading="Skills">
    <div class="skills-container">
        <div class="frontend">
            <h2>Frontend</h2>
            <div class="skills">
                <div class="skill">
                    <Html/>
                    <h3>Html</h3>
                </div>
                <div class="skill">
                    <Css/>
                    <h3>CSS</h3>
                </div>
                <div class="skill">
                    <Javascript />
                    <h3>Javascript</h3>
                </div>
                <div class="skill">
                    <React />
                    <h3>React</h3>
                </div>
                <div class="skill">
                    <Svelte />
                    <h3>Svelte</h3>
                </div>
            </div>
        </div>
        <div class="backend">
            <h2>Backend</h2>
            <div class="skills">
                <div class="skill">
                    <Python />
                    <h3>Python</h3>
                </div>
                <div class="skill">
                    <Go />
                    <h3>Go</h3>
                </div>
                <div class="skill">
                    <C />
                    <h3>C</h3>
                </div>
                <div class="skill">
                    <NodeJs />
                    <h3>Node.js</h3>
                </div>
                <div class="skill">
                    <Express />
                    <h3>ExpressJS</h3>
                </div>
                <div class="skill">
                    <Flask />
                    <h3>Flask</h3>
                </div>
            </div>
        </div>
        <div class="database">
            <h2>Datenbanken</h2>
            <div class="skills">
                <div class="skill">
                    <Sqlite />
                    <h3>Sqlite</h3>
                </div>
                <div class="skill">
                    <MySql />
                    <h3>MySQL</h3>
                </div>
            </div>
        </div>
    </div>
</HeadingContainer>
<HeadingContainer heading="Projekte">
    <div class="projects-container">
        <Project
            src="/videos/Kanu.webm"
            liveProject="https://kanu-oderbruch.de"
            projectLink="https://github.com/M-U-16/Kanuseite"
        >
            <h2 slot="head">Kanuverleih Infoseite</h2>
            Eine einfache statische Webseite für den
            Kanuverleih von meinem Vater.
        </Project>        
    </div>
</HeadingContainer>
<Footer />

<script>
    import Flask from "$lib/icons/Flask.svelte"
    import MySql from "$lib/icons/MySql.svelte"
    import Sqlite from "$lib/icons/Sqlite.svelte"
    import C from "$lib/icons/C.svelte"
    import NodeJs from "$lib/icons/NodeJs.svelte"
    import Express from "$lib/icons/Express.svelte"
    import Go from "$lib/icons/Go.svelte"
    import Python from "$lib/icons/Python.svelte"
    import Javascript from "$lib/icons/Javascript.svelte"
    import Svelte from "$lib/icons/Svelte.svelte"
    import React from "$lib/icons/React.svelte"
    import Css from "$lib/icons/Css.svelte"
    import Html from "$lib/icons/Html.svelte"
    
    import HeadingContainer from "$lib/components/heading-container.svelte";
    import Footer from "$lib/components/Footer.svelte"
    import Header from "$lib/Header.svelte";
    import Project from "$lib/components/Project.svelte"
</script>

<style>
    .projects-container {
        width: 100%;
        min-height: 30vh;
        margin: 1rem 0;
    }

    :global(.skill .icon svg) {
        width: 3rem;
    }

    .backend,
    .database {
        margin-top: 1rem
    }

    .skills {
        display: flex;
        gap: 0.5rem;
        flex-wrap: wrap;
    }
    
    .skills .skill {
        padding: 1rem;
        border-radius: 5px;
        background-color: white;
        box-shadow: inset 0px 0px 2px rgb(181, 181, 181);
    }

    .skills .skill h3 {
        text-align: center;
    }
</style>