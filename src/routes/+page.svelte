<Header />
<HeadingContainer heading="Über mich">
    <div class="about-me">
        <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nesciunt culpa error, sunt commodi cum qui nobis id corrupti fuga ducimus fugit architecto laboriosam iste, ex, illum libero magnam omnis porro rerum odit! Voluptatum rerum tempore dolorem repellendus dicta exercitationem itaque, nam praesentium minima nihil minus. Eum voluptate commodi veniam veritatis?
        </p>
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
        <Project
            src="/videos/chat_800.mp4"
            liveProject="https://easychat.maurice-ueberfeld.de"
            projectLink="https://github.com/M-U-16/EasyChat"
        >
            <h2 slot="head">EasyChat</h2>
            EasyChat ist eine einfache Chat Anwendung die,
            mithilfe von Websockets (<a href="https://socket.io" target="_blank">Socket.IO</a>),
            eine textbasierte Echtzeit Unterhaltung ermöglicht.
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

    /* .view-more {
        width: 100%;
        padding: 0.8rem;
        text-align: center;
        grid-column: span 2;
        border-radius: 5px;
        border: 1px solid var(--accent-color);
        text-decoration: none;
    } */

    .about-me p {
        font-size: 1.2rem;
    }

    @media screen and (max-width: 900px) {
        .projects-container {
            display: flex;
            flex-direction: column;
        }
    }
</style>