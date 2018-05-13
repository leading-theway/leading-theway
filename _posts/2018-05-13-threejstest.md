---
layout:        post
title:         "My first three.js app"
date:          2018-05-13
author:        "Author"
header-img:    "img/mypic1.jpg"
tags:          3D
categories:    3D Simulation
---

<div>
    <script src = "/build/three.min.js"> </script>
		<script>
			//Javascript goes here.
			var camera, scene, renderer;
			var geometry, material, mesh;
			init();
			animate();
			function init() {
			camera = new THREE.PerspectiveCamera( 70, window.innerWidth / window.innerHeight, 0.01, 10 );
			camera.position.z = 1;
			scene = new THREE.Scene();
			geometry = new THREE.BoxGeometry( 0.2, 0.2, 0.2 );
			material = new THREE.MeshNormalMaterial();
			mesh = new THREE.Mesh( geometry, material );
			scene.add( mesh );
			renderer = new THREE.WebGLRenderer( { antialias: true } );
			renderer.setSize( window.innerWidth, window.innerHeight );
			document.body.appendChild( renderer.domElement );
			}
			function animate() {
			requestAnimationFrame( animate );
			mesh.rotation.x += 0.01;
			mesh.rotation.y += 0.02;
			renderer.render( scene, camera );
			}
	</script>
  
</div>
