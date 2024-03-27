<script>
    import menu from '$lib/assets/burgermenu.svg'
    let menuOpen = false;

    function toggleMenu() {
        menuOpen = !menuOpen;
    }
</script>

<header>
    <nav>
        <div class="flex-nav">
            <h3>ESCAPE.</h3>

            <button class="burger" on:click={toggleMenu}>
                <img src="{menu}" alt="menu burger">
            </button>
        </div>
        <div class="nav {menuOpen ? 'open' : ''}">
            <a href="#carte" class="nav-elt"><span>Carte</span></a>
            <a href="#modele" class="nav-elt"><span>Modèle</span></a>
        </div>

        
    </nav>
</header>

<style>
    .burger {
        background: transparent;
        border: none;
        cursor: pointer;
        padding: 0;
        z-index: 10;
    }

    .nav {
        display: none;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 5px;
    }

    h3 {
        color: #617285;
    }

    .nav.open {
        display: flex;
    }

    .flex-nav {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        padding: 20px;
        align-items: center;
    }

    .nav-elt span {
        color: #617285;
        font-size: large;
    }

    @media (min-width: 768px) {
        .burger {
            opacity: 0;
        }

        .nav {
            display: flex;
            top: 20px;
            right: 20px;
            position: absolute;
            opacity: 1;
            flex-direction: row;
            gap: 15px;
        }
    }

</style>