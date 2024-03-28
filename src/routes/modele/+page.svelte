<script>
    import Footer from '../../components/Footer.svelte';
    import Header from '../../components/Header.svelte';
</script>

<Header />

<div class="container">
    <iframe title="Coffre" frameborder="0" allowfullscreen mozallowfullscreen="true" webkitallowfullscreen="true" allow="autoplay; fullscreen; xr-spatial-tracking" xr-spatial-tracking execution-while-out-of-viewport execution-while-not-rendered web-share src="https://sketchfab.com/models/3cfc78911c104450bde5212518b5d2aa/embed"> </iframe>
    <h3>Le Langskip</h3>
</div>

<div class="article">
    <p>Lorem ipsum dolor sit amet consectetur. Pulvinar urna viverra interdum pharetra. Magnis tincidunt ut accumsan enim malesuada volutpat metus. Scelerisque in arcu purus volutpat ipsum sit. Bibendum porta amet viverra suspendisse arcu. Ultricies malesuada arcu tortor tincidunt. Nisi justo velit nunc aliquam proin scelerisque id id. Vel pretium enim metus eleifend amet. Vitae ac cursus aliquet faucibus vel nibh sem ligula pellentesque. Sem nec gravida id risus id massa scelerisque est. Tempor ut sodales sit tristique condimentum id magna. Non sed turpis arcu viverra turpis aliquet in vitae tortor.</p>
</div>
<Footer />

<style>
    .container {
        margin: 10px auto;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-color: #617285;
        padding: 20px 0;
        color: #fff;
        gap: 10px;
    }

    iframe {
        width: 256px;
        height: 144px;
    }

    h3 {
        font-size: medium;
    }

    .article {
        text-align: justify;
        width: 90%;
        margin: 30px auto;

    }

    @media (min-width: 768px) {
        .container {
            width: 97%;
            border-radius: 1.4em;
        }

        iframe {
            width: 426px;
            height: 240px;
        }
    }

    @media (min-width: 1024px) {
        iframe {
            width: 800px;
            height: 450px;
        }

        .container {
            padding: 40px 0;
        }

        h3 {
            font-size: 1.4em;
        }
        
    }

    @media (min-width: 1440px) {
        iframe {
            width: 960px;
            height: 540px;
        }
    }
</style>