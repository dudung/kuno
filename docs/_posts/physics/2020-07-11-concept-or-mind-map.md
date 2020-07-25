---
layout: post
author: viridi
title: Concept map or mind map
mathjax: true
ptext: false
x3dom: false
threejs: false
category: physics
tags: ["idea"]
date: 2020-07-11 19:54:00 +07
<!--permalink: physics-->
---
Which to use as the main page of physics pages

## Prologue
In the Dave's HyperPhysics [[1](#ref1)] a mind map is used to relate the topics in physics. Perhaps there is assumption that a topic can only be preceeded by one topic in delivering the material through lecture. But when the assumption is different, e.g. a topic can be preceeded by two or more topics, a concept maps is better. Concept maps include cross-connection between concepts, while mind maps are always radial, brached out with a central topic [[2](#ref2)].

## JS or SVG?
The maps can be built using JavaScript (JS) and drawn on HTML DOM canvas object or Scalable Vector Graphics (SVG) and used directly on HTML. Or JS to create SVG?

<script>
var svgns = "http://www.w3.org/2000/svg";
var svg = document.createElementNS(svgns, "svg");
svg.setAttributeNS(null, "width", "200");
svg.setAttributeNS(null, "height", "100");
svg.style = "border:1px dashed black";
var rect = document.createElementNS(svgns, "rect");
rect.setAttributeNS(null, "x", "10");
rect.setAttributeNS(null, "y", "10");
rect.setAttributeNS(null, "width", "80");
rect.setAttributeNS(null, "height", "30");
rect.setAttributeNS(null, "rx", "8");
rect.setAttributeNS(null, "ry", "8");
rect.rx = "8";
rect.ry = "8";
rect.width = "80";
rect.height = "30";
rect.style = "fill:#bfb;stroke:black;stroke-width:2;opacity:1.0";
svg.append(rect);
document.body.append(svg);
</script>

<svg width="200" height="100" style="border:1px dashed black">
<rect x="10" y="10" rx="8" ry="8" width="80" height="30"
  style="fill:#bfb;stroke:black;stroke-width:2;opacity:1.0" />
<rect x="110" y="10" rx="8" ry="8" width="80" height="30"
  style="fill:#bfb;stroke:black;stroke-width:2;opacity:1.0" />

<foreignobject x="10" y="10" width="80" height="40">
		<body xmlns="http://www.w3.org/1999/xhtml">
				<div style="text-align:center;vertical-align:middle;height:40px"><a href="/physics/kinematics">Kinematika</a></div>
		</body>
</foreignobject>
</svg>

sdfds


<!--svg width="200" height="100">
<rect x="10" y="10" rx="8" ry="8" width="80" height="30"
  style="fill:#bfb;stroke:black;stroke-width:2;opacity:1.0" />
<rect x="110" y="10" rx="8" ry="8" width="80" height="30"
  style="fill:#bfb;stroke:black;stroke-width:2;opacity:1.0" />

<foreignobject x="10" y="10" width="80" height="40">
		<body xmlns="http://www.w3.org/1999/xhtml">
				<div style="text-align:center;vertical-align:middle;height:40px"><a href="/physics/kinematics">Kinematika</a></div>
		</body>
</foreignobject>
</svg>

<svg width="100" height="100">
  <rect width="30" height="40" style="fill:rgb(0,0,255);stroke-width:3;stroke:rgb(0,0,0)" />
  <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" />
  <text x="0" y="15" fill="red">I love SVG!</text>
  <rect x="50" y="20" width="15" height="15" style="fill:blue;stroke:pink;stroke-width:5;fill-opacity:0.1;stroke-opacity:0.9" />
<rect x="50" y="20" rx="3" ry="3" width="20" height="30"
  style="fill:red;stroke:black;stroke-width:2;opacity:0.5" />

  <g>
    <rect x="0" y="0" width="100" height="100" fill="red"></rect>
    <text x="0" y="50" font-family="Verdana" font-size="35" fill="blue">Hello</text>
  </g>
	
</svg>

<svg width="250" height="250" xmlns="http://www.w3.org/2000/svg">
		<rect x="0" y="0" width="250" height="250" fill="aquamarine" />
		<foreignobject x="10" y="10" width="250" height="250">
				<body xmlns="http://www.w3.org/1999/xhtml">
						<div>Here is a long text that runs more than one line and works as a paragraph</div>
						<br />
						<div>This is <u>UNDER LINE</u> one</div>
						<br />
						<div>This is <b>BOLD</b> one</div>
						<br />
						<div>This is <i>Italic</i> one <a href="/physics/kinematics">Kinematika</a></div>
				</body>
		</foreignobject>
</svg-->

## Items
1. mechanics
2. fluids
3. waves
4. electromagnetics
5. modern physics

## Note
Created on 20200711. Jekyll page accomodate also permalink [[3](#ref3)] that can be used to developed a HyperPhysics-like [[1](#ref1)] or Wikipedia-like [[4](#ref4)] pages.

## References
2. <a name="ref2"></a>Carl Rod Nave, "HyperPhysics", HyperPhysics, 2016, url <http://hyperphysics.phy-astr.gsu.edu/hbase/index.html> [20200711].
1. <a name="ref1"></a> Kristina Gjorgievska, "The Differences Between Mind Maps and Concept Maps", iMindQ, 12 Jul 2018, url <https://www.imindq.com/blog/differences-between-mind-maps-and-concept-maps> [20200707].
3. <a name="ref3"></a>David Jacquel, "Answert to 'Jekyll Filename Without Date'", Stack Overflow, 24 Nov 2014, url https://stackoverflow.com/a/27101060/9475509 [20200711].
4. <a name="ref4"></a>Wikipedia contributors, "Portal:Physics", Wikipedia, The Free Encyclopedia, 06 Jul 2020, url <https://en.wikipedia.org/w/index.php?title=Portal:Physics&oldid=966319508>
