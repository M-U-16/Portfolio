<Header />
<HeadingContainer heading="Über mich" id="about_me">
    <div class="about-me">
        <p>
            Ich konnte mich schon immer für verschiedene Programmiersprachen
            und Themen im Bereich der Programmierung begeistern.
            Als ich zum ersten mal herausgefunden habe wie man
            eine Webseite erstellt, war ich davon fasziniert und
            habe angefangen mich intensiv mit HTML und CSS zu beschäftigen,
            um meine Fähigkeiten in der Web-Entwicklung zu verbessern.
            Durch kleine Projekte und erste Berührungspunkten mit Javascript Bibliotheken wie z.B.
            <a href="https://webpack.js.org">Webpack</a> zum ersten mal
            habe ich, mehr oder weniger, verstanden
            wie HTML und CSS mithilfe von Javascript verändert
            werden können.
        </p>
    </div>
</HeadingContainer>
<HeadingContainer heading="Projekte">
    <div class="projects-container">
        <Project
            type="video/webm"
            src="/videos/Kanu.webm"
            liveProject="https://kanu-oderbruch.de"
            projectLink="https://github.com/M-U-16/Kanuseite"
        >
            <h2 slot="head">Kanuverleih Infoseite</h2>
            <p slot="description">
                Eine einfache statische Webseite für den
                Kanuverleih von meinem Vater.
            </p>
            <div slot="techs">
                <h4>Technologien:</h4>
                <p>Svelte</p>
            </div>
        </Project>
        <Project
            type="video/mp4"
            src="/videos/chat_800.mp4"
            liveProject="https://easychat.maurice-ueberfeld.de"
            projectLink="https://github.com/M-U-16/EasyChat"
        >
            <div slot="techs">
                <h4>Technologien:</h4>
                <p>Svelte, Typescript, Nodejs (Express)</p>
            </div>
            <h2 slot="head">EasyChat</h2>
            <p slot="description">
                EasyChat ist eine einfache Chat Anwendung die,
                mithilfe von Websockets (<a href="https://socket.io" target="_blank">Socket.IO</a>),
                eine textbasierte Echtzeit Unterhaltung ermöglicht.
            </p>
            <span slot="live-link">Test Seite</span>
        </Project>
    </div>
</HeadingContainer>
<Skills />
<Footer />

<script>
    import Skills from "$lib/Skills.svelte"
    import Footer from "$lib/Footer.svelte"
    import Header from "$lib/Header.svelte"
    import Project from "$lib/components/Project.svelte"
    import HeadingContainer from "$lib/container/heading-container.svelte";

</script>

<style>
    .projects-container {
        display: grid;
        gap: 1rem;
        grid-template-columns: 1fr 1fr;
        
        width: 100%;
        min-height: 30vh;
    }

    .about-me {
        transform: translateY(-5px);
    }

    .about-me p {
        font-size: 1.2rem;
    }

    :global(#about_me) {
        scroll-margin: var(--navbar-height);
    }

    @media screen and (max-width: 900px) {
        .projects-container {
            display: flex;
            flex-direction: column;
        }
    }

    @media screen and (max-width: 380px) {
        .projects-container {
            gap: 0;
        }
    }
</style>