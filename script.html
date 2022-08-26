<div class="product-card-3d-view-container">
    <div class="progress-bar-container">
        <progress id="progress-bar" val="0" max="100"></progress>
    </div>
    <canvas id="product-card-3d-view" width='100%' height='100%'></canvas>
</div>

<style>
    .product-card-3d-view-container {
        position: relative;
        width: 780px;
        height: 580px;
        overflow: hidden;
    }
    .progress-bar-container {
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;
        background: #000;
        width: 100%;
        height: 100%;
    }
    .progress-bar-label {
        color: white;
    }
    #progress-bar {
        width: 30%;
        height: 2%;
    }
</style>

<script type="module">
import * as THREE from 'three';
import { GLTFLoader } from 'GLTFLoader';
import { OrbitControls } from 'OrbitControls';
import { RGBELoader } from 'RGBELoader';

// import { EffectComposer } from 'EffectComposer';
// import * as RenderPass from 'RenderPass';
// import * as FilmPass from 'FilmPass';
// import * as BloomPass from 'BloomPass';

let scene, camera, renderer, controls, composer;

let isRotate = true;

let mouseX = 0, mouseY = 0;

let windowHalfX = window.innerWidth / 2;

let windowHalfY = window.innerHeight / 2;

const canvasContainer = document.querySelector('.product-card-3d-view-container');
console.log({d: canvasContainer});
let size = {w: canvasContainer.clientWidth, h: canvasContainer.clientHeight } ;

function init() {
    const loadingManager = new THREE.LoadingManager();

    const progressbar = document.querySelector('#progress-bar');
    loadingManager.onProgress = (url, loaded, total) => {
        progressbar.value = (loaded / total) * 100;
    };
    loadingManager.onLoad = () => {
        console.log(progressbar.parentNode);
        progressbar.parentNode.style.display = 'none';
    };


    scene = new THREE.Scene();
    const textureCube = new THREE.CubeTextureLoader().load( [
		'https://i.ibb.co/smpvHh3/S-c04.png',
		'https://i.ibb.co/P9vrsZM/S-c05.png',
		'https://i.ibb.co/Bqb1k4G/S-c02.png',
		'https://i.ibb.co/VJpzfR3/S-c03.png',
		'https://i.ibb.co/GnvPV4K/S-c00.png',
		'https://i.ibb.co/MVMzRXC/S-c01.png'
	] );
	textureCube.magFilter = THREE.LinearFilter;
    textureCube.minFilter = THREE.LinearMipMapLinearFilter;
    textureCube.format = THREE.RGBFormat;
    textureCube.encoding = THREE.sRGBEncoding;
    textureCube.anisotropy = 16;
	textureCube.format = THREE.RGBFormat;
    // textureCube.mapping = THREE.CubeRefractionMapping;
    scene.background = textureCube;
	scene.fog = new THREE.Fog(0x5d0361, 10, 1500);
    // scene.background = new THREE.Color(0xff0000);
    camera = new THREE.PerspectiveCamera(45, size.w / size.h, 0.01, 5000);
    camera.position.set(0, 0, .5);

    const canvas = document.querySelector('#product-card-3d-view');
    renderer = new THREE.WebGLRenderer({canvas, antialias: true, alpha: true});
    renderer.setPixelRatio( window.devicePixelRatio );
    renderer.setSize(size.w, size.h);
    renderer.gammaOutput = true;
    renderer.outputEncoding = THREE.sRGBEncoding
    renderer.shadowMap.enabled = true;
    renderer.shadowMapType = THREE.PCFSoftShadowMap;
    // renderer.toneMapping = THREE.ReinhardToneMapping;
    renderer.toneMapping = THREE.LinearToneMapping;
	renderer.toneMappingExposure = 1;
	renderer.outputEncoding = THREE.sRGBEncoding;
    console.log(renderer);
    controls = new OrbitControls(camera, canvas);
    controls.enablePan = false;
    controls.autoRotate = true;
	controls.enableDamping = true;
	controls.minDistance = .2;
	controls.maxDistance = .8;
    controls.update();
    
    // lights

// 	const hemiLight = new THREE.HemisphereLight( 0xffffff, 0x444444 );
// 	hemiLight.position.set( 0, 1, 0 );
// 	scene.add( hemiLight );

    const hemiLight = new THREE.HemisphereLight('#f7f6e3', 0x080820, 1);
    scene.add(hemiLight);
    
    const light = new THREE.SpotLight('#fffbf4', .8);
    light.position.set(-50,50,50);
    light.castShadow = true;
    scene.add( light );
    
    light.shadow.bias = -0.0001;
    light.shadow.mapSize.width = 1024*4;
    light.shadow.mapSize.height = 1024*4;
    
    // scene.add( new THREE.CameraHelper( light.shadow.camera ) );

////////////////////////////
//     const light = new THREE.RectAreaLight('#eeecd8', 3, 10, 10);
//     light.position.set(1, 50, 1);
//     light.rotation.x = THREE.MathUtils.degToRad(-60);
//     light.rotation.y = THREE.MathUtils.degToRad(20);
//     light.rotation.z = THREE.MathUtils.degToRad(-20);
//     scene.add(light);

	const dirLight = new THREE.DirectionalLight( 0xffffff, .5 );
	dirLight.position.set(0, 2, 0);
	dirLight.castShadow = true;
	dirLight.shadow.camera.top = 0.5;
	dirLight.shadow.camera.bottom = - 0.5;
	dirLight.shadow.camera.left = - 0.5;
	dirLight.shadow.camera.right = 0.5;
	dirLight.shadow.camera.near = 1;
	dirLight.shadow.radius = 12;
	dirLight.shadow.bias = -0.0001;
    dirLight.shadow.mapSize.width = 1024*4;
    dirLight.shadow.mapSize.height = 1024*4;
	dirLight.shadow.camera.far = 4;
	dirLight.shadow.mapSize.set( 1024, 1024 );
	scene.add( dirLight );

// 	scene.add( new THREE.CameraHelper( dirLight.shadow.camera ) );
    
    createLights();
    // const light = new THREE.DirectionalLight( 0xffffff, 5 );
    // light.position.set( .2, 1, 0 ); //default; light shining from top
    // light.castShadow = true; // default false
    // scene.add( light );
    
    //Set up shadow properties for the light
    // light.shadow.mapSize.width = 512; // default
    // light.shadow.mapSize.height = 512; // default
    // light.shadow.camera.near = 0.5; // default
    // light.shadow.camera.far = 500; // default

    // const hlight = new THREE.AmbientLight(0x404040, 100);
    // scene.add(hlight);

    // const directionalLight = new THREE.DirectionalLight(0xffffff, 50);
    // directionalLight.position.set(0,1,0);
    // directionalLight.castShadow = true;
    // scene.add(directionalLight);

    // const light = new THREE.PointLight(0xc4c4cc4, 10);
    // light.position.set(0, 300, 500);
    // light.castShadow = true;
    // scene.add(light);

    // const light2 = new THREE.PointLight(0xc4c4cc4, 2);
    // light.position.set(500, 100, 0);
    // scene.add(light2);

    // const light3 = new THREE.PointLight(0xc4c4cc4, 2);
    // light.position.set(0, 100, -500);
    // scene.add(light3);

    // const light4 = new THREE.PointLight(0xc4c4cc4, 2);
    // light.position.set(-5000, 300, 0);
    // scene.add(light4);


    //controls = new THREE.OrbitControls(camera, renderer.domElement);
    canvas.addEventListener( 'mousedown', startHandler, false );
    canvas.addEventListener( 'mouseup', endHandler, false );
    canvas.addEventListener( 'touchstart', startHandler, false );
    canvas.addEventListener( 'touchend', endHandler, false );
    // document.addEventListener( 'touchmove', onDocumentTouchMove, false );
    // window.addEventListener( 'resize', onWindowResize, false );
    const mat = new THREE.ShadowMaterial();
    mat.opacity = .2;
    const mesh = new THREE.Mesh( new THREE.PlaneBufferGeometry( 100, 100 ), mat);
    mesh.position.set(0, -.2, 0);
	mesh.rotation.x = - Math.PI / 2;
	mesh.receiveShadow = true;
	mesh.castShadow = true;
	scene.add( mesh );
    
    // const geo = new THREE.PlaneBufferGeometry(2000, 2000, 8, 8);
    // const mat = new THREE.MeshBasicMaterial({ color: 0x404040 });
    // const plane = new THREE.Mesh(geo, mat);
    // plane.rotateX( - Math.PI / 2);
    // scene.add(plane);
    
    // const composer = new EffectComposer(renderer);
    // composer.addPass(new RenderPass(scene, camera));
    
    // const bloomPass = new BloomPass(
    //     1,    // strength
    //     25,   // kernel size
    //     4,    // sigma ?
    //     256,  // blur render target resolution
    // );
    // composer.addPass(bloomPass);
    
    // const filmPass = new FilmPass(
    //     0.35,   // noise intensity
    //     0.025,  // scanline intensity
    //     648,    // scanline count
    //     false,  // grayscale
    // );
    // filmPass.renderToScreen = true;
    // composer.addPass(filmPass);
    
    new RGBELoader().load('https://threejs.org/examples/textures/equirectangular/royal_esplanade_1k.hdr', (texture) => {
        scene.environment = texture;
    });

    const loader = new GLTFLoader(loadingManager);
    loader.load('https://raw.githubusercontent.com/privalenkov/models/main/product1/bk.gltf', function(gltf) {
        gltf.scene.traverse( function ( node ) {

			if ( node.type === 'Mesh' ) {
				node.castShadow = true;
				node.receiveShadow = true;
				node.material.metalness = 0; // undo this change if you apply an env map
                if(node.material.map) node.material.map.anisotropy = 16; 

			}

		} );
        console.log(gltf, camera)
        const product = gltf.scene.children[0];
        product.magFilter = THREE.LinearFilter;
        product.minFilter = THREE.LinearMipMapLinearFilter;
        product.format = THREE.RGBFormat;
        product.encoding = THREE.sRGBEncoding;
        product.anisotropy = 16;
    	product.format = THREE.RGBFormat;
        product.scale.set(.0005,.0005,.0005);
        product.position.set(0, -.65, 0);
        scene.add(gltf.scene);
        animate();
    }, function ( xhr ) {
		console.log( ( xhr.loaded / xhr.total * 100 ) + '% loaded' );
	});

}


const createLights = () => {
//   const ambientLight = new THREE.HemisphereLight('#f0ebe4', '#f0ebe4', .5);

  const directionalLight = new THREE.DirectionalLight('#fff9e6', .3);
  directionalLight.position.set(-300, 0, 600);
  console.log(directionalLight);
// 0xffa95c
  const pointLight = new THREE.PointLight('#ffffff', 1, 1000, 1);
  pointLight.position.set(10, -50, 10);
  
//   const pointLight2 = new THREE.PointLight('#ffffff', 3, 5000, 3);
//   pointLight2.position.set(120, 100, 120);
//   console.log(pointLight2);
//   scene.add( new THREE.CameraHelper( pointLight2.shadow.camera ) );
//   console.log(pointLight);

  scene.add(directionalLight, pointLight);
};

function startHandler () {
    if (controls.autoRotate) { 
        controls.autoRotate = false 
    };
    
}

function endHandler () {
    let timeout;
    if (!controls.autoRotate && !timeout) { 
        timeout = setTimeout(() => {
            controls.autoRotate = true;
        }, 2000);
    };
    
    
}

function animate () {
    requestAnimationFrame(animate);

	controls.update();
// 	composer.render();

	renderer.render(scene, camera);
}

init()

</script>
