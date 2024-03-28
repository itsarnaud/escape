<script>
    import github from '$lib/assets/github.svg';
</script>

<footer>
    <div class="git">
        <div class="git-elt">
            <span>Arnaud</span>
            <a href="https://github.com/itsarnaud"><img src="{github}" alt="Logo github"></a>
        </div>
        <div class="git-elt">
            <span>Timothé</span>
            <a href="https://github.com/Fvrenn"><img src="{github}" alt="Logo github"></a>
        </div>
    </div>
    <p>© 2024 Copyright</p>
</footer>

<style>
    footer {
        margin-top: 50px;
        background-color: #617285;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        color: #fff;
        gap: 15px;
        padding: 20px 0;
    }

    .git {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 35px;
    }

    .git-elt {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 10px;
    }

    .git-elt img {
        width: 20px;
        height: auto;
        transition-duration: .5s;

        &:hover {
            transform: scale(1.1);
        }
    }

    p:hover {
        text-decoration: underline;
    }

    @media (min-width: 768px) {
        footer {
            width: 97%;
            margin: 50px auto 10px auto;
            border-radius: 1.4em;
        }
        
        span {
            font-size: large;
        }

        .git-elt img {
            width:25px;
            height: auto;
        }

        .git {
            gap: 50px;
        }
    }

    @media (min-width: 768px) {
        span {
            font-size: larger;
        }

        .git {
            gap: 80px;
        }
    }

</style>