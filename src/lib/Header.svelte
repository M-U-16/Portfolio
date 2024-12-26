<div
    class="header-container"
>
    <header>
        <div class="text">
            <h1 class="heading">
                Hallo, ich bin Maurice,
                angehender Softwareentwickler und Technikbegeisterter.
            </h1>
            <p>
                Zurzeit bin ich dabei mein Abitur zu machen.
                Für meinen Weg nach dem Abitur, suche ich nach
                einem Unternehmen, bei dem ich meine Leidenschaft, das Programmieren,
                auch beruflich ausführen kann und mein Wissen in den Bereichen der
                Softwareentwicklung zu erweitern. 
            </p>
        </div>
        <div class="links">
            <a href="https://github.com/M-U-16/" target="_blank">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 512 512"
                >
                    <path
                        d="M256 32C132.3 32 32 134.9 32 261.7c0 101.5 64.2 187.5 153.2 217.9a17.56 17.56 0 003.8.4c8.3 0 11.5-6.1 11.5-11.4 0-5.5-.2-19.9-.3-39.1a102.4 102.4 0 01-22.6 2.7c-43.1 0-52.9-33.5-52.9-33.5-10.2-26.5-24.9-33.6-24.9-33.6-19.5-13.7-.1-14.1 1.4-14.1h.1c22.5 2 34.3 23.8 34.3 23.8 11.2 19.6 26.2 25.1 39.6 25.1a63 63 0 0025.6-6c2-14.8 7.8-24.9 14.2-30.7-49.7-5.8-102-25.5-102-113.5 0-25.1 8.7-45.6 23-61.6-2.3-5.8-10-29.2 2.2-60.8a18.64 18.64 0 015-.5c8.1 0 26.4 3.1 56.6 24.1a208.21 208.21 0 01112.2 0c30.2-21 48.5-24.1 56.6-24.1a18.64 18.64 0 015 .5c12.2 31.6 4.5 55 2.2 60.8 14.3 16.1 23 36.6 23 61.6 0 88.2-52.4 107.6-102.3 113.3 8 7.1 15.2 21.1 15.2 42.5 0 30.7-.3 55.5-.3 63 0 5.4 3.1 11.5 11.4 11.5a19.35 19.35 0 004-.4C415.9 449.2 480 363.1 480 261.7 480 134.9 379.7 32 256 32z"
                    />
                </svg>
                <span>Github</span>
            </a>
        </div>
    </header>
    <div class="style-element">
        <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 100 100"
            preserveAspectRatio="none"
        >
            <polygon points="0,100 100,0 100,100"/>
            <line
                x1="0" y1="100" x2="100" y2="0"
                stroke="var(--accent-color)"
                stroke-width="1"
                stroke-opacity="0.08"
            />
        </svg>
    </div>
</div>

<script>
</script>

<style>
    .header-container {
        position: relative;
        display: flex;
        height: 50vh;
        min-height: 30rem;
        align-items: center;
        background: url(/reduced-topography.svg);
        background-position: 0 0;
        background-attachment: fixed;
        view-transition-name: header-container;
        transition: 0.1s linear;
    }
    
    header {
        margin: auto;
        width: var(--default-width);
        view-transition-name: header;
        font-size: 18px;
        max-width: var(--default-max-width);
    }
    
    header .heading {
        text-wrap: balance;
    }

    .text p {
        line-height: 1.3;
    }

    .links {
        margin: 1rem 0 0 0;
    }

    .links a {
        width: 10rem;;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 1.2rem;
        background-color: black;
        color: white;
        padding: 0.5rem;
        border-radius: 5px;
        border: none;
        gap: 0.5rem;
        text-decoration: none;
        cursor: pointer;
    }

    .links a svg {
        height: 2rem;
        width: 2rem;
        fill: white;
    }

    .style-element {
        position: absolute;
        bottom: 0;
        width:100%;
        height: 5rem;
    }

    .style-element svg {
        width: 100%;
        height: 100%;
    }

    .style-element svg polygon {
        fill: var(--bg-color);
    }

    @media screen and (max-width: 900px) {
        header .heading {
            font-size: 1.8rem;
        }
    }

    @media screen and (max-width: 500px) {
        .header-container {
            height: 50vh;
        }

        header .text p {
            line-height: 1.2;
        }
    }
</style>