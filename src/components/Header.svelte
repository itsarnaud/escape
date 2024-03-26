<script>
    let menuOpen = false;
    import menu from '$lib/assets/burgermenu.svg';

    const toggleMenu = () => {
        menuOpen = !menuOpen;
    }

</script>

<header>
    <nav>
        <h3>ESCAPE.</h3>
        <button on:click={toggleMenu}><img src={menu} alt="burgerbutton"></button>
        <div class="nav">
            <a href="#carte" class="nav-elt"><span>Carte</span></a>
            <a href="#modele" class="nav-elt"><span>Modèle</span></a>
        </div>
    </nav>
</header>

<style>
    nav {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
        padding: 20px 30px;
    }

    h3 {
        font-weight: 700;
        color: #617285;
        font-size: 1.4em;
    }

    .nav-elt {
        position: relative;
        margin: 0 10px;
        font-size: 1.1em;
        cursor: pointer;
        color: #617285;
        transition: .5s;

        &::after {
            content: "";
            position: absolute;
            bottom: -5px;
            left: 0;
            border-radius: 10px;
            width: 100%;
            height: 2px;
            background: #617285;
            transform: scaleX(0);
            transform-origin: right;
            transition: transform .4s ease-in-out;
        }

        &:hover {
            &::after {
                transform: scaleX(1);
                transform-origin: left;
            }
        }
    }

    /* nav a {
        margin: 40% 10px;
        font-size: x-large;
        transform: translateX(20px);
        cursor: pointer;
        transition: .5s;
        opacity: 0;

        &::after {
            position: absolute;
            content: "";
            top: 90%;
            left: 0;
            width: 100%;
            height: 2px;
            background: #EDDBC7;
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.5s;
            border-radius: 10px;
        }

        &:hover {
            color: #EDDBC7;
        }
        
        &:hover::after {
            transform: scaleX(1);
            transform-origin: left;
        }
    
    } */
</style>