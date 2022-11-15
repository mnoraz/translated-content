<!doctype html>
<html>

<head>
	<title>Radar Chart</title>
	<script src="Chart.bundle.js"></script>
	<script src="utils.js"></script>
	<style>
		canvas {
			-moz-user-select: none;
			-webkit-user-select: none;
			-ms-user-select: none;
		}
	</style>
</head>

<body>
	<div style="width:80%">
		<canvas id="canvas"></canvas>
	</div>
	
	<?php
	$lbl_dataSet2019="Audit SI 2019";
	$lbl_dataSet2020="Point SI 2020";
	$lbl_dataSet2021="Point SI 2021";
	$lbl_dataSet2022="Point SI 2022";

	$html= " <button id='DatasetInit'>$lbl_dataSet2019</button>";
	$html.= " <button id='addDataset2020'>$lbl_dataSet2020</button>";
	$html.= " <button id='addDataset2021'>$lbl_dataSet2021</button>";
	$html.= " <button id='addDataset2022'>$lbl_dataSet2022</button>";
	echo $html;
	
?>
	<script>
		var randomScalingFactor = function() {
			return Math.round(Math.random() * 100);
		};

		var color = Chart.helpers.color;
		var config = {
			type: 'radar',
			data: {
				labels: [['Hébergement', 'DataCenter'], ['Cablâge', 'réseau interne'], 
						'Parc d ordinateurs', ['Téléphonie', 'IP'], 
						'Vidéo-conférence', 'Sécurité', 'FireWall','Sauvegarde', 
						'Messagerie', 'RGPD'], 
				datasets: [{
					label: 
<?php
					echo "'$lbl_dataSet2019'";				
?>
					,
					backgroundColor: color(window.chartColors.red).alpha(0.2).rgbString(),
					borderColor: window.chartColors.red,
					pointBackgroundColor: window.chartColors.red,
					data: [
						50,  // 1- hébergement
						80,  // 2- cablage
						10,  // 3 - parc informatique
						30,  // 4 - telephonie
						10,  // 5 - video-conf
						10,  // 6 - securite
						10,  // 7 - fire wall
						10,  // 8 - sauvegarde
						10,  // 9 - messagerie
						10   // 10 - RGPD
					]
				}, {
					label: 
<?php
					echo "'$lbl_dataSet2020'";
					
?>
					,
					backgroundColor: color(window.chartColors.blue).alpha(0.2).rgbString(),
					borderColor: window.chartColors.blue,
					pointBackgroundColor: window.chartColors.blue,
					data: [
						50,  // 1- hébergement
						80,  // 2- cablage
						90,  // 3 - parc informatique
						30,  // 4 - telephonie
						50,  // 5 - video-conf
						40,  // 6 - securite
						50,  // 7 - fire wall
						40,  // 8 - sauvegarde
						100,  // 9 - messagerie
						20   // 10 - RGPD
					]
				}]
			},
			options: {
				legend: {
					position: 'top',
				},
				title: {
					display: true,
					text: 'Evolution du système d\'information: suit à l\'audit de juin 2019'
				},
				scale: {
					ticks: {
						beginAtZero: true
					}
				}
			}
		};

		window.onload = function() {
			window.myRadar = new Chart(document.getElementById('canvas'), config);
		};

		document.getElementById('randomizeData').addEventListener('click', function() {
			config.data.datasets.forEach(
			function(dataset) 
			{
				dataset.data = dataset.data.map(
				function() {
					return randomScalingFactor();
				});
			});

			window.myRadar.update();
		});

		var colorNames = Object.keys(window.chartColors);
		//======================================================  adddata 2020
		document.getElementById('addDataset2020').addEventListener('click', function() {
			var colorName = colorNames[config.data.datasets.length % colorNames.length];
			var newColor = window.chartColors[colorName];
 
			var newDataset = {
				label: 
<?php
					echo "'$lbl_dataSet2020'";
					
?>
				,
				borderColor: newColor,
				backgroundColor: color(newColor).alpha(0.2).rgbString(),
				pointBorderColor: newColor,
				data: [],
			};
			 	newDataset.data.push(10); // 1 hébergement
				newDataset.data.push(80); // 2 cablage
				newDataset.data.push(80); // 3 parc informatique
				newDataset.data.push(80); // 4 telephonie
				newDataset.data.push(80); // 5 - video-conf
				newDataset.data.push(80); // 6 - securite
				newDataset.data.push(80); // 7 - fire wall
				newDataset.data.push(80); // 8 - sauvegarde
				newDataset.data.push(80); // 9 - messagerie
				newDataset.data.push(80); // 10 - RGPD
			//}

			config.data.datasets.push(newDataset);
			window.myRadar.update();
		});
		// adddata 2022
		document.getElementById('addDataset2022').addEventListener('click', function() {
			var colorName = colorNames[config.data.datasets.length % colorNames.length];
			var newColor = window.chartColors[colorName];
 
			var newDataset = {
				label: 
<?php
					echo "'$lbl_dataSet2022'";
					
?>
				,
				borderColor: newColor,
				backgroundColor: color(newColor).alpha(0.2).rgbString(),
				pointBorderColor: newColor,
				data: [],
			};
			 	newDataset.data.push(10); // 1 hébergement
				newDataset.data.push(80); // 2 cablage
				newDataset.data.push(80); // 3 parc informatique
				newDataset.data.push(80); // 4 telephonie
				newDataset.data.push(80); // 5 - video-conf
				newDataset.data.push(80); // 6 - securite
				newDataset.data.push(80); // 7 - fire wall
				newDataset.data.push(80); // 8 - sauvegarde
				newDataset.data.push(80); // 9 - messagerie
				newDataset.data.push(80); // 10 - RGPD
			//}

			config.data.datasets.push(newDataset);
			window.myRadar.update();
		});
// adddata 2021
		document.getElementById('addDataset2021').addEventListener('click', function() {
			var colorName = colorNames[config.data.datasets.length % colorNames.length];
			var newColor = window.chartColors[colorName];
 
			var newDataset = {
				label: 'Point SI 2021',
				borderColor: newColor,
				backgroundColor: color(newColor).alpha(0.2).rgbString(),
				pointBorderColor: newColor,
				data: [],
			};
			 	newDataset.data.push(10); // 1 hébergement
				newDataset.data.push(80); // 2 cablage
				newDataset.data.push(80); // 3 parc informatique
				newDataset.data.push(80); // 4 telephonie
				newDataset.data.push(80); // 5 - video-conf
				newDataset.data.push(80); // 6 - securite
				newDataset.data.push(80); // 7 - fire wall
				newDataset.data.push(80); // 8 - sauvegarde
				newDataset.data.push(80); // 9 - messagerie
				newDataset.data.push(80); // 10 - RGPD
			//}

			config.data.datasets.push(newDataset);
			window.myRadar.update();
		});

		// Ajouter des données
	/* 	document.getElementById('addData').addEventListener('click', function() {
			if (config.data.datasets.length > 0) {
				config.data.labels.push('dataset #' + config.data.labels.length);
				alert("ok");
				 config.data.dataset.push(90);
				 config.data.dataset.push(90);
				 
				/*config.data.datasets.forEach(
					function(dataset) {
						dataset.data.push(randomScalingFactor());
					});
		 
				window.myRadar.update();
			}
		});
*/
		// masquer des données
		document.getElementById('removeDataSet').addEventListener('click', function() {
			config.data.datasets.splice(0, 1);
			window.myRadar.update();
		});

		document.getElementById('removeData').addEventListener('click', function() {
			config.data.labels.pop(); // remove the label first

			config.data.datasets.forEach(function(dataset) {
				dataset.data.pop();
			});

			window.myRadar.update();
		});
	</script>
</body>

</html>
