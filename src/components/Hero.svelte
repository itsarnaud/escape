<script>
    import arrow from '$lib/assets/arrow.svg';
</script>

<div class="test">
    <h3>Scandinavie.</h3>
    <img src="{arrow}" alt="fleche">
</div>

<style>
    .test {
        background-image: url(../lib/assets/Vikings.jpg);
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        width: 100%;
        height: 80vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    h3 {
        color: #fff;
        font-size: 1.4em;
    }

    img {
        position: absolute;
        bottom: 20%;
        width: 20px;
        height: auto;
    }

    @media (min-width: 768px) {
        .test {
            border-radius: 1.4em;
            width: 97%;
            margin: 1px auto;
        }

        h3 {
            font-size: 1.9em;
        }

        img {
            width: 24px;
            height: auto;
        }
        
    }

    @media (min-width: 1440px) {
        .test {
            height: 85vh;
        }

        h3 {
            font-size: 2.8em;
        }
    }

</style>

