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
            Durch kleine Projekte und ersten Berührungspunkten mit Javascript Bibliotheken wie z.B.
            <a href="https://webpack.js.org" target="_blank">Webpack</a> habe ich zum ersten Mal,
            verstanden wie HTML und CSS mithilfe von Javascript verändert
            werden können und welche Möglichkeiten es für die Gestaltung von Webseiten bietet.
        </p>
        <p>
            Nachdem ich mich zuerst nur mit der Frontend Entwicklung
            beschäftigt habe, fing ich auch mit der Backend Entwicklung an.
            Ich experimentierte mit verschiedenen Frameworks in Python und JavaScript,
            beschäftigte mich mit Datenbanken sowie deren Verbindung zum Backend und Frontend.
        </p>
        <p>
            Zurzeit beschäftige ich mich mit der Programmierung
            in C und Go und dem Hosting von Servern auf meinem privaten
            <a
                href="https://en.wikipedia.org/wiki/Virtual_private_server"
                target="_blank"
            >VPS</a>.
        </p>
    </div>
</HeadingContainer>
<HeadingContainer>
    <div slot="heading" class="projects-headings">
        <h1 id="projekte">Projekte</h1>
        <h2>(an denen ich zurzeit Arbeite)</h2>
    </div>
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
            <p slot="techs">
                <b>Technologien:</b>
                <span>Svelte</span>
            </p>
        </Project>
        <Project
            type="video/mp4"
            src="/videos/chat_800.mp4"
            projectLink="https://github.com/M-U-16/EasyChat"
        >
            <!-- liveProject="https://easychat.maurice-ueberfeld.de" -->
            <h2 slot="head">EasyChat</h2>
            <p slot="description">
                EasyChat ist ein privates Projekt,
                welches aus einer einfachen Chat Anwendung besteht, die,
                mithilfe von Websockets (<a href="https://socket.io" target="_blank">Socket.IO</a>),
                eine textbasierte Echtzeit Unterhaltung ermöglicht.
            </p>
            <p slot="techs">
                <b>Technologien:</b>
                <span>Svelte, Typescript, Nodejs (Express), SQlite</span>
            </p>
           <!--  <span slot="live-link">Test Seite</span> -->
        </Project>
        <Project
            type="video/mp4"
            src="/videos/dashboard_800.mp4"
            projectLink="https://github.com/M-U-16/Wetterstation"
        >
            <h2 slot="head">Wetterstation</h2>
            <p slot="description">
                Die Wetterstation ist ein Projekt, an dem
                ich im Rahmen des Informatik-Unterrichts arbeite.
                Es geht um die Erfassung von verschiedenen Sensordaten
                wie Temperatur und Luftfeuchtigkeit über einen Raspberry-Pi und die Darstellung
                dieser in einem Web-Interface.
            </p>
            <p slot="techs">
                <b>Technologien:</b>
                <span>Python, Flask, Javascript (D3.js), SQlite</span>
            </p>
            <span slot="live-link">Test Seite</span>
        </Project>
        <Project
            type="video/mp4"
            src="/videos/player_800.mp4"
            projectLink="https://github.com/M-U-16/MediaPlayer"
        >
            <h2 slot="head">MediaPlayer</h2>
            <p slot="description">
                MediaPlayer ist ein privates Projekt,
                bei dem es um die Verarbeitung von verschiedenen
                Medien wie Audio -und Videodatein geht.
            </p>
            <p slot="techs">
                <b>Technologien:</b>
                <span>C (SDL2, FFMPEG)</span>
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
        margin-top: 1rem;
    }

    .about-me p:first-child {
        margin: 0;
    }

    :global(#about_me) {
        scroll-margin: var(--navbar-height);
    }

    .projects-headings {
        padding: 1rem 0;
    }

    .projects-headings h1 {
        padding: 0;
        font-size: 2rem;
        font-weight: 500;
        font-stretch: expanded;
        color: var(--accent-color);
        scroll-margin: var(--navbar-height);
    }
    
    .projects-headings h2 {
        padding: 0;
        font-size: 1rem;
        font-weight: 500;
        font-stretch: expanded;
        color: var(--accent-color);
    }

    @media screen and (max-width: 900px) {
        .projects-container {
            display: flex;
            flex-direction: column;
        }
    }

    @media screen and (max-width: 500px) {
        .about-me p {
            font-size: 1rem;
        }

        .projects-headings h1 {
            font-size: 1.6rem;
        }
    }

    @media screen and (max-width: 380px) {
        .projects-container {
            gap: 0;
        }
    }
</style>