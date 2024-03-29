<script>
    import { onMount } from 'svelte';
    import * as THREE from 'three';
    import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js';
    import Header from '../../components/Header.svelte';
    import Footer from '../../components/Footer.svelte';

    let container;

    onMount(async () => {
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const light = new THREE.AmbientLight(0xffffff); // lumière blanche
        scene.add(light);   
        const renderer = new THREE.WebGLRenderer();
        let obj;

        renderer.setSize(container.clientWidth, container.clientHeight);
        container.appendChild(renderer.domElement);

        const loader = new GLTFLoader();
        loader.load('/landskip.glb', function(gltf) {
            console.log("Ça marche !!");
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
                obj.rotation.y += 0.01; // changez cette valeur pour ajuster la vitesse de rotation
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
    <div class="iframe" bind:this={container}></div>
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

    .iframe {
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
    }
</style>