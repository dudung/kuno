---
layout: post
author: viridi
title: pendahuluan
mathjax: true
chartjs: true
ptext: true
x3dom: true
threejs: true
3dmol: true
category: introduction
tags: ["introduction"]
date: 2020-07-22 19:43:00 +07
permalink: introduction
---
Penjelasan perihal teks ini, fisika -- <i>physics in plain text</i> (id)


## Text datar
Semua ingin dituliskan dalam bentuk teks datar (plain text) sehingga ukuran tulisa menjadi kecil dan mudah dikirimkan.


## Pustaka yang digunakan
Terdapat beberapa pustakan yang digunakan sebagaimana telah diindikasikan dengan icon pada bagian sebelum judul tulisan.

### MathJax
Dengan menggunakan MathJax akar dari persamaan $y = ax^2 + bx + c$ dapat dituliskan

\begin{equation}
\label{eqn:square-formula}
x_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a},
\end{equation}

di mana Eqn. \eqref{eqn:square-formula} diperoleh dengan

```latex
\begin{equation}
\label{eqn:square-formula}
x_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a},
\end{equation}
```

### Chart.js
Diagram berikut

<canvas id="myChart" width="400" height="400"></canvas>
<script>
var can = document.getElementById('myChart');
can.width = "200px !important";
var ctx = can.getContext('2d');

var scatterChart = new Chart(ctx, {
    type: 'scatter',
    data: {
        datasets: [{
            label: 'Scatter Dataset',
            data: [
							{ x: -10, y: 0 }, 
							{ x: 0, y: 10 },
							{ x: 10, y: 5 }
						]
        }]
    },
    options: {
        scales: {
            xAxes: [{
                type: 'linear',
                position: 'bottom'
            }]
        }
    }
});
</script>

dapat diperoleh dengan


### ptext
Kurva berikut ini
<ptext>
{ // xy-chart
	version: "0.0.8",
	label: "fig-siqnal-square",
	caption: "Isyarat segiempat dengan pText",
	background: "#fff0f0",
	width: 200,
	height: 100,
	data: {
		x: [1, 1, 20, 20, 40, 40, 60, 60, 80, 80, 100, 100, 110, 110, 120, 120, 130, 130, 140, 140, 150, 150, 160, 160, 170, 170, 180, 180, 190, 190, 199, 199],
		y: [0, 100, 100, 0, 0, 100, 100, 0, 0, 100, 100, 0, 0, 100, 100, 0, 0, 100, 100, 0, 0, 100, 100, 0, 0, 100, 100, 0, 0, 100, 100, 0],
	},
	type : "line",
	color: {
		line: "#f00",
		point: "#0e0",
	},
}
</ptext>

dapat diperoleh dengan

```javascript
<ptext>
{ // xy-chart
	version: "0.0.8",
	label: "fig-siqnal-square",
	caption: "Graph with points",
	background: "#fafffa",
	width: 200,
	height: 100,
	data: {
		x: [1, 1, 20, 20, 40, 40, 60, 60, 80, 80, 100, 100, 110,
		110, 120, 120, 130, 130, 140, 140, 150, 150, 160, 160,
		170, 170, 180, 180, 190, 190, 199, 199],
		y: [0, 100, 100, 0, 0, 100, 100, 0, 0, 100, 100, 0, 0,
		100, 100, 0, 0, 100, 100, 0, 0, 100, 100, 0, 0, 100, 100,
		0, 0, 100, 100, 0],
	},
	type : "line",
	color: {
		line: "#f00",
		point: "#0e0",
	},
}
</ptext>
```

### X3DOM
Visualisasi berikut

<script>
	var x3d = document.createElement("x3d");
	var scene = document.createElement("scene");
	var transform = document.createElement("transform");
	var shape = document.createElement("shape");
	var appearance = document.createElement("appearance");
	var material = document.createElement("material");
	var sphere = document.createElement("sphere");
	
	x3d.setAttribute("width","200px");
	x3d.setAttribute("height", "200px");
	transform.setAttribute("translation", "0 0 7");
	material.setAttribute("diffuseColor", "0 0.5 1");
	
	document.body.append(x3d);
	x3d.append(scene);
	scene.append(transform);
	transform.append(shape);
	shape.append(appearance);
	appearance.append(material);
	shape.append(sphere);
</script>

diperoleh dengan

```javascript
<script>
	var x3d = document.createElement("x3d");
	var scene = document.createElement("scene");
	var transform = document.createElement("transform");
	var shape = document.createElement("shape");
	var appearance = document.createElement("appearance");
	var material = document.createElement("material");
	var sphere = document.createElement("sphere");
	
	x3d.setAttribute("width","200px");
	x3d.setAttribute("height", "200px");
	transform.setAttribute("translation", "0 0 7");
	material.setAttribute("diffuseColor", "0 0.5 1");
	
	document.body.append(x3d);
	x3d.append(scene);
	scene.append(transform);
	transform.append(shape);
	shape.append(appearance);
	appearance.append(material);
	shape.append(sphere);
</script>
```

### Three.js
Gambar berikut

<script>
var width = 400;
var height = 200;
var scene = new THREE.Scene();
scene.background = new THREE.Color(0xffffff);
var camera = new THREE.PerspectiveCamera(75, width/height, 0.1, 1000);
 
var renderer = new THREE.WebGLRenderer({alpha: true});
renderer.setSize(width, height);

var geometry = new THREE.SphereGeometry(20, 18, 18);

var material = new THREE.MeshPhongMaterial(
	{
		color: 0x555555,
		emissive: 0x0077cc,
		wireframe: false,
	}
);
var sphere = new THREE.Mesh(geometry, material);
scene.add(sphere);

var color = 0xffffff;
var intensity = 1;
var light = new THREE.DirectionalLight(color, intensity);
light.position.set(0, 0, 3);
light.target.position.set(-1, -2, 0);
scene.add(light);
scene.add(light.target);
 
camera.position.z = 35;
camera.position.x = 0;

var axis = new THREE.Vector3(1, 0, 0);
var dist = 2;
sphere.translateOnAxis(axis, dist);

renderer.render(scene, camera);

document.body.appendChild(renderer.domElement);
</script>

diperoleh dengan

```javascript
<script>
var width = 400;
var height = 200;
var scene = new THREE.Scene();
scene.background = new THREE.Color(0xffffff);
var camera = new THREE.PerspectiveCamera(75, width/height, 0.1, 1000);
 
var renderer = new THREE.WebGLRenderer({alpha: true});
renderer.setSize(width, height);

var geometry = new THREE.SphereGeometry(20, 18, 18);

var material = new THREE.MeshPhongMaterial(
	{
		color: 0x555555,
		emissive: 0x0077cc,
		wireframe: false,
	}
);
var sphere = new THREE.Mesh(geometry, material);
scene.add(sphere);

var color = 0xffffff;
var intensity = 1;
var light = new THREE.DirectionalLight(color, intensity);
light.position.set(0, 0, 3);
light.target.position.set(-1, -2, 0);
scene.add(light);
scene.add(light.target);
 
camera.position.z = 35;
camera.position.x = 0;

var axis = new THREE.Vector3(1, 0, 0);
var dist = 2;
sphere.translateOnAxis(axis, dist);

renderer.render(scene, camera);

document.body.appendChild(renderer.domElement);
</script>
```

### 3Dmol.js
Visualisasi molekul berikut ini

<div style="height: 400px; width: 400px; position: relative;" class='viewer_3Dmoljs' data-pdb='1YCR' data-backgroundcolor='0xffffff' 
        data-select1='chain:A' data-style1='cartoon:color=spectrum' data-surface1='opacity:.7;color:white' data-select2='chain:B' data-style2='stick'></div>

Fig 1 Contoh molekul 1YCR dalam 3Dmol viewer.

dipeorleh dengan

```javascript
<div
	style="height: 400px; width: 400px; position: relative;" 

	class='viewer_3Dmoljs'

	data-pdb='1YCR'
	data-backgroundcolor='0xffffff' 

	data-select1='chain:A'
	data-style1='cartoon:color=spectrum'
	data-surface1='opacity:.7;color:white'

	data-select2='chain:B'
	data-style2='stick'
>
</div>
```

## Referensi
1. <a name="ref1"></a> "3Dmol.js", url https://3dmol.csb.pitt.edu [20200609].
(https://threejs.org/docs/).
