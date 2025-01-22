<div class="contacts">
    <h2 class="standard-heading">Kontakt</h2>
    <div class="all-contacts">
        <div class="tel-container">
            <div class="contact">
                <a href="tel:+491797618554">
                    <Call />
                    <span>Anrufen*</span>
                </a>
                <div class="text">
                    <p>+49 179 7618554</p>
                </div>
            </div>
        </div>
        <div class="contact">
            <a href="mailto:maurice-u@gmx.de">
                <Mail />
                <span>Mailen</span>
            </a>
            <div class="text">
                <p>maurice-u@gmx.de</p>
            </div>
        </div>
    </div>
    <div class="contact-time">
        <p>*Montag bis Freitag: ab 17 Uhr (während der Schulzeit)</p>
        <p>Wochenende: i.d.R offen</p>
    </div>
</div>

<script>
    import Call from "$lib/icons/Call.svelte"
    import Mail from "$lib/icons/Mail.svelte"

</script>

<style>
    .contacts {
        /* padding: 1rem 2rem; */
        padding: 2rem 0;
        width: 100%;
    }

    .contacts h2 {
        color: var(--accent-color);
    }
    
    .contact {
        display: flex;
        margin: 0.5rem 0;
        overflow: 1;
        align-items: center;
        border-radius: 0 5px 5px 0;
        background-color: rgba(132, 132, 255, 0.149);
    }
    
    .contact a {
        display: flex;
        justify-content: space-start;
        align-items: center;
        gap: 0.5rem;
        background-color: var(--accent-color);
        color: white;
        text-decoration: none;
        padding: 0.5rem 1rem;
        border-radius: 5px 0 0 5px;
        width: 7.5rem;
    }

    .contact a span {
        display: flex;
    }
    
    .contact .text {
        overflow: hidden;
        padding: 0 1rem 0 1rem;
    }
    
    .contact-time {
        color: grey;
    }

    @media screen and (min-width: 900px) {
        .all-contacts {
            display: flex;
            width: 100%;
            gap: 1rem;
        }
    }    

    @media screen and (max-width: 380px) {
        .contacts {
            padding: 1rem;
        }
    }
</style>