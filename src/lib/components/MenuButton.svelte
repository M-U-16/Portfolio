<button
    class="hamburger-button"
    class:active={active}
    id="navbar-hamburger-btn"
    on:click={toggleMenu}
    aria-label="Menü öffnen"
>
    <span class="hamburger-layer"></span>
    <span class="hamburger-layer"></span>
    <span class="hamburger-layer"></span>
</button>

<script>
    export let active
    export let toggleMenu = () => {}
</script>

<style>
.hamburger-button {
    display: none;
    cursor: pointer;
    position: relative;
    flex-direction: column;
    background-color: transparent;
    border: none;
    width: 1.5rem;
    height: 1.3rem;
    /* margin-right: 1rem; */
    z-index: 3;
    overflow: hidden;
    outline: none;
}

.hamburger-layer {
    display: block;
    width: 100%;
    height: 3px; 
    background-color: var(--accent-color);
    position: absolute;
    right: 0;
    margin-left: auto; margin-right: auto;
    transition: translate 0.3s ease;
}

.hamburger-button span:nth-child(1) {
    top: 2px;
}

.hamburger-button span:nth-child(2) {
    top: 50%;
    transform: translateY(-50%);
}

.hamburger-button span:nth-child(3) {
    bottom: 2px;
}

.hamburger-button.active span:nth-child(1) {
    top: 50%;
    transform:
        translateY(-50%)
        rotate(45deg);
    width: 110%;
}

.hamburger-button.active span:nth-child(2) {
    opacity: 0;
}

.hamburger-button.active span:nth-child(3) {
    bottom: 50%;
    transform:
        translateY(50%)
        rotate(-45deg);
    width: 110%;
}

@media (max-width: 500px) {
    .hamburger-button {
        display: flex;
    }
}
</style>