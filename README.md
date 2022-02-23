<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>VoltLab - Casino</title>
		<style>
		body{
			width:100%;height:100%;
		}
		
		html{
			width:100%;height:100%;
		}
		* { 
		padding: 0; 
			margin: 0; 
			background-color:black;
		}
		#scene {
			position: relative;
			width: 1013px;
			height: 859px;
			margin:auto;
		}
		#menu {
			position: absolute;
			width: 100%;
			height: 100%;
			margin:auto;
			background-color:black;
			z-index: 7;
		}
		canvas { 
			position: absolute;
			top: 0;
			left: 0;
			background-color: transparent;
		}
		#intro
		{
			transition: all 0.1s linear;
		}
		#layerBackground {
			z-index: 1 
		}
		#layerBattery {
			z-index: 2 
		}
		#layerConnections {
			z-index: 3 
		}
		#layerResult {
			z-index: 4 
		}
		.fadeOut {
			display: none;
			opacity: 0;
		}
		</style>
	</head>
	<body>
		
		<div id="menu" onClick="start()" >
			<img src="img/HACKERMANS.png" style="margin:auto; display:block; margin-top: 360px;" />
		</div>
		
		
		<div id="intro" style="z-index:6; display:none; position:absolute; background-color:#101010; width:100%; height:100%;">
			<img style="position:absolute;top:0;bottom:80px;right:0;left:0;margin:auto; z-index:7 " src="img/intro.gif"  />
		</div>

		<div id="badEnding" style="z-index:6; display:none; position:absolute; background-color:#101010; width:100%; height:100%;">
			<img style="position:absolute;top:0;bottom:80px;right:0;left:0;margin:auto; z-index:7 " src="img/fail.gif"  />
		</div>

		<div id="goodEnding" style="z-index:6; display:none; position:absolute; background-color:#101010; width:100%; height:100%;">
			<img style="position:absolute;top:0;bottom:80px;right:0;left:0;margin:auto; z-index:7 " src="img/success.gif"  />
		</div>

		<div id="scene">
		  <canvas id="layerBackground" width="1013" height="859"></canvas>
		  <canvas id="layerBattery" width="1013" height="859"></canvas>
		  <canvas id="layerConnections" width="1013" height="859"></canvas>
		  <canvas id="layerResult" width="1013" height="859"></canvas>
		  <img src="img/controls.png" style="margin-top:850px; margin-left:440px;"/>
		</div>

	</body>
	
	<script type="text/javascript" src="voltlab.js"></script>

	<script>
	var vl = new VoltLab();
	
	function start()
	{
		loading_sound.play();
		document.getElementById("menu").style.display="none";
		document.getElementById("intro").style.display="block";
		window.setTimeout(function() {
		document.getElementById("intro").classList.toggle('fadeOut');
		vl.start();
	  }, 3200); 
	}
	</script>
</html>
