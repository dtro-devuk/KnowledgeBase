#### *A curated list of helpful material to start learning Modern Development Things

<!DOCTYPE HTML>
<html>

<head>
<meta charset="UTF-8">
<title>Canvas Snow Effect</title>
<style type="text/css">

body {
	background: #6b92b9;
}
canvas {
	display: block;
}

</style>

<body>
	
<canvas id="canvas"></div>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
<script type="text/javascript">

$(document).ready(function(){
window.onload = function(){
	//canvas init
	var canvas = document.getElementById("canvas");
	var ctx = canvas.getContext("2d");
	
	//canvas dimensions
	var W = window.innerWidth;
	var H = window.innerHeight;
	canvas.width = W;
	canvas.height = H;
	
	//snowflake particles
	var mp = 25; //max particles
	var particles = [];
	for(var i = 0; i < mp; i++)
	{
		particles.push({
			x: Math.random()*W, //x-coordinate
			y: Math.random()*H, //y-coordinate
			r: Math.random()*4+1, //radius
			d: Math.random()*mp //density
		})
	}
	
	//Lets draw the flakes
	function draw()
	{
		ctx.clearRect(0, 0, W, H);
		
		ctx.fillStyle = "rgba(255, 255, 255, 0.8)";
		ctx.beginPath();
		for(var i = 0; i < mp; i++)
		{
			var p = particles[i];
			ctx.moveTo(p.x, p.y);
			ctx.arc(p.x, p.y, p.r, 0, Math.PI*2, true);
		}
		ctx.fill();
		update();
	}
	
	//Function to move the snowflakes
	//angle will be an ongoing incremental flag. Sin and Cos functions will be applied to it to create vertical and horizontal movements of the flakes
	var angle = 0;
	function update()
	{
		angle += 0.01;
		for(var i = 0; i < mp; i++)
		{
			var p = particles[i];
			//Updating X and Y coordinates
			//We will add 1 to the cos function to prevent negative values which will lead flakes to move upwards
			//Every particle has its own density which can be used to make the downward movement different for each flake
			//Lets make it more random by adding in the radius
			p.y += Math.cos(angle+p.d) + 1 + p.r/2;
			p.x += Math.sin(angle) * 2;
			
			//Sending flakes back from the top when it exits
			//Lets make it a bit more organic and let flakes enter from the left and right also.
			if(p.x > W+5 || p.x < -5 || p.y > H)
			{
				if(i%3 > 0) //66.67% of the flakes
				{
					particles[i] = {x: Math.random()*W, y: -10, r: p.r, d: p.d};
				}
				else
				{
					//If the flake is exitting from the right
					if(Math.sin(angle) > 0)
					{
						//Enter from the left
						particles[i] = {x: -5, y: Math.random()*H, r: p.r, d: p.d};
					}
					else
					{
						//Enter from the right
						particles[i] = {x: W+5, y: Math.random()*H, r: p.r, d: p.d};
					}
				}
			}
		}
	}
	
	//animation loop
	setInterval(draw, 33);
}

})

</script>

</body>
</html>


#### IoT

* [Cool Things to buy on Amazon](https://www.youtube.com/watch?v=PdLBRPkZObA&sns=em)

###Artificial Inteligence

###Augmented Reality

###Proximity Marketing

####Modern Web Development

### Angular 2 
* [Official Angular 2 Design Docs (Google)](https://drive.google.com/drive/folders/0B7Ovm8bUYiUDR29iSkEyMk5pVUk)
* [Official Angular 2 - 5 min quickstart](https://angular.io/docs/js/latest/quickstart.html)
* [Angular 2 Education Rsources](https://github.com/timjacobi/angular2-education)
* [Awesome Angular 2](https://github.com/AngularClass/awesome-angular2)

## Key Concepts
* [Thinking in Angular 2 -  an overview of concepts for JavaScript developers on youtube](https://youtu.be/XlqoPpLMdwY)

## Angular 2 Modules
* [Quick Start Tutorial on youtube](https://youtu.be/L0XXoPqSphs)

## Components
* [Responding to component events(Rangle.io)](https://angular-2-training-book.rangle.io/handout/components/app_structure/responding_to_component_events.html)

## Projection/ Transclusion
* [Using Ng-Content (Scotch.io) ](https://scotch.io/tutorials/angular-2-transclusion-using-ng-content)

##RxJS
* [RxJS Crash Course on youtube](https://youtu.be/ei7FsoXKPl0)
* [Angular Introduction to Reactive Extensions (RxJS)](https://medium.com/google-developer-experts/angular-introduction-to-reactive-extensions-rxjs-a86a7430a61f#.1o4tur21g)

## Apps
* [Angular JS Chat with Loopback](https://www.codetutorial.io/angularjs-chat-whit-socket-io-and-loopback/)
* [MEAN Stack App on youtube] (https://youtu.be/tYkb2Qu4UmM)
* [Build your Angular 2 App: From Auth to calling an API (Auth0.com)](https://auth0.com/blog/creating-your-first-real-world-angular-2-app-from-authentication-to-calling-an-api-and-everything-in-between/)


#### Cascading Style Sheets

## REM units
* [Understanding REM units (Sitepoint)](https://www.sitepoint.com/understanding-and-using-rem-units-in-css/)

#### HTML 5

## Canvas
*[HTML5 Canavas Tutorials.com](http://www.html5canvastutorials.com/)

### JavaScript


### TypeScript


### Node JS


####Mobile Development

### NativeScript

* [The Ultimate Guide For Building RTA (Mean Expert)](http://mean.expert/2016/06/09/angular-2-ultimate-real-time/)

#### Cloud and SaaS

### Azure

### AWS

###Facebook Messnger

