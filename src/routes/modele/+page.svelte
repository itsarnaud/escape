<script>
    import { onMount } from 'svelte';
    import * as THREE from 'three';
    import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js';
    import Header from '../../components/Header.svelte';
    import Footer from '../../components/Footer.svelte';

    let container;
    let isLoading = true;
    let startTime;

    onMount(async () => {
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const light = new THREE.AmbientLight(0xffffff); // lumière blanche
        scene.add(light);   
        const renderer = new THREE.WebGLRenderer();
        let obj;

        renderer.setSize(container.clientWidth, container.clientHeight);
        container.appendChild(renderer.domElement);

        startTime = performance.now();
        const loader = new GLTFLoader();
        console.log('ça charge...');
        loader.load('https://langskip.s3.eu-west-3.amazonaws.com/landskip.glb', function(gltf) {
            let endTime = performance.now();
            let loadingTime = (endTime - startTime) / 1000;
            console.log(`Le modèle a fini de charger en ${loadingTime} secondes.`);
            isLoading = false;
            obj = gltf.scene;
            scene.add( obj );
        }, undefined, function ( error ) {
            console.error( error );
        } );

        camera.position.z = 70;
        camera.position.y = 20;

        const animate = function() {
            requestAnimationFrame(animate);
            if (obj) {
                obj.rotation.y += 0.005;
            }
            renderer.render(scene, camera);
        };

        window.addEventListener('resize', function() {
            renderer.setSize(container.clientWidth, container.clientHeight);
            camera.aspect = container.clientWidth / container.clientHeight;
            camera.updateProjectionMatrix();
        });

        animate();
    });
</script>

<Header />
<div class="container">
    {#if isLoading}
        <p style="text-align: center; padding: 0 10px">Chargement du modèle en cours. Cela peux prendre plusieurs minutes selon votre connexion internet...</p>
    {/if}
    <div class="iframe" bind:this={container}></div>
    <h3>Le Langskip</h3>
</div>



<div class="article">
    <h4>Le Langskip : Symbole de puissance et d'ingéniosité nordique</h4>
    <p>Dans les récits d'antan, plane l'ombre majestueuse du Langskip, symbole de l'audace des Scandinaves. Contrairement à la croyance populaire, le fameux "drakkar" n'a jamais existé. Il s'agit en réalité du Langskip, popularisé par l'officier napoléonien Auguste Jal dans son ouvrage de 1848.</p>
    <p>Le Langskip n'était pas qu'un simple moyen de transport, mais un outil de conquête. Mesurant jusqu'à 50 mètres de long pour 8 mètres de large, sa robustesse n'avait d'égal que son agilité.</p>
    <p>Construit selon des méthodes ancestrales, le Langskip était constitué de planches superposées, renforcées par des rivets en fer. Cette technique, le bordage à clin, lui conférait une solidité à toute épreuve, défiant les tempêtes les plus féroces.</p>
    <p>La voile, initialement négligée, devint rapidement un élément crucial de la navigation viking à bord du Langskip. Permettant d'exploiter les vents pour accélérer les déplacements, elle fut adoptée en complément des rameurs réguliers.</p>
    <p>Doté d'une quille, innovation majeure, le Langskip pouvait naviguer avec stabilité et précision, même dans les eaux les plus agitées. Cette pièce de bois, fixée sous la coque, assurait une meilleure tenue de cap et facilitait les manœuvres.</p>
    <p>À bord du Langskip, les Vikings ont tracé des routes commerciales à travers l'Europe, bravant les éléments pour découvrir de nouveaux horizons. Leur héritage perdure, le Langskip demeurant le témoin immuable de leur courage et de leur ténacité marine.</p>
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

    .iframe {
        width: 256px;
        height: 144px;
    }

    h3 {
        font-size: medium;
    }

    .article {
        text-align: justify;
        width: 70%;
        margin: 30px auto;

    }

    .article p {
        margin: 10px 0;
    }

    .article h4 {
        font-size: large;
    }

    @media (min-width: 768px) {
        .container {
            width: 97%;
            border-radius: 1.4em;
        }

        .iframe {
            width: 426px;
            height: 240px;
        }
    }

    @media (min-width: 1024px) {
        .iframe {
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
        .iframe {
            width: 960px;
            height: 540px;
        }

        .article p {
            font-size: 1.2em;
        }

        .article h4 {
            font-size: 1.6em;
        }
    }
</style>