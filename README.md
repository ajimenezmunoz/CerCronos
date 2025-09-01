<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cron&oacute;metros Certificaci&oacute;n</title>
  <style>
  body{
    font: 20px/1.5 "Helvetica Neue", Helvetica, Arial, sans-serif;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    background-color: #fff;
    color: #000;
  }
   
  .timer {
    display: flex;
    justify-content: space-evenly;
    align-items: evenly;
    min-width: 50vw;
    padding: 10px;
    border-width: 0.5px 0.5px;
    border-style: solid;
    border-color: #ffffff;
    margin-bottom: 200px;  
    background-color: #e8eaf6;
    color: #000;
  }
   
  .timerContainer{
    justify-content: center;
    align-items: evenly;
    display: flex;
    min-width: 50vw;
  }
   
  h2{
    margin-top: 0px;
  }
   
  h1 {
    font-size: 300%;
  }
   
  #controls{
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
    min-width: 50vw;
    margin-top: 10px;
	padding: 10px 10px 10px 10px;
  }
   
  span{
    /* Tamaño relojes */ 
	font-size: 1000%;
    text-align: left;
  }
   
  h4{
    font-size: 250%;
    margin-top: 0px;
    margin-bottom: 0px;
    text-align: left;
  }

  .timerButton{
    background-color: #6745c2;
    color: white;
    border: solid 0.5px white;
    padding: 10px 10px 10px 10px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 180%;
    margin: 4px 2px;
    width: 200px;
  }

  .timerButton:hover {
    background-color: white;
    color: #6745c2;
    border: solid 0.5px #6745c2;
  }
  
    .timerButtonSmall{
    background-color: #6745c2;
    color: white;
    border: solid 0.5px white;
    padding: 10px 10px 10px 10px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 150%;
    margin: 4px 2px;
    width: 100px;
  }

  .timerButtonSmall:hover {
    background-color: white;
    color: #6745c2;
    border: solid 0.5px #6745c2;
  }
  </style>
  <script type="text/javascript" defer>var time_list = [
    // Temporizadores A2
	{ id: "timer-1", timername: "Preparación mon&oacute;logo A2", time: 120, status: "stop", original: 120 },
	{ id: "timer-2", timername: "Mon&oacute;logo A2", time: 120, status: "stop", original: 120 },
	{ id: "timer-3", timername: "Preparación Interacci&oacute;n A2", time: 60, status: "stop", original: 60 },
	{ id: "timer-4", timername: "Interacci&oacute;n parejas A2", time: 240, status: "stop", original: 240 },
	{ id: "timer-5", timername: "Interacci&oacute;n tr&iacute;o A2", time: 360, status: "stop", original: 360 },
	{ id: "timer-6", timername: "Preparaci&oacute;n mediaci&oacute;n A2", time: 120, status: "stop", original: 120 },
	{ id: "timer-7", timername: "Mediaci&oacute;n A2", time: 90, status: "stop", original: 90 },
	// Temporizadores B1
	{ id: "timer-8", timername: "Preparación mon&oacute;logo B1<a id='B1'></a>", time: 120, status: "stop", original: 120 },
	{ id: "timer-9", timername: "Mon&oacute;logo B1", time: 150, status: "stop", original: 150 },
	{ id: "timer-10", timername: "Preparación Interacci&oacute;n B1", time: 60, status: "stop", original: 60 },
	{ id: "timer-11", timername: "Interacci&oacute;n parejas 	B1", time: 240, status: "stop", original: 240 },
	{ id: "timer-12", timername: "Interacci&oacute;n tr&iacute;o B1", time: 360, status: "stop", original: 360 },
	{ id: "timer-13", timername: "Preparaci&oacute;n mediaci&oacute;n B1", time: 180, status: "stop", original: 180 },
	{ id: "timer-14", timername: "Mediaci&oacute;n B1", time: 120, status: "stop", original: 120 },
	// Temporizadores B2
	{ id: "timer-15", timername: "Preparación mon&oacute;logo B2<a id='B2'></a>", time: 120, status: "stop", original: 120 },
	{ id: "timer-16", timername: "Mon&oacute;logo B2", time: 180, status: "stop", original: 180 },
	{ id: "timer-17", timername: "Preparación Interacci&oacute;n B2", time: 120, status: "stop", original: 120 },
	{ id: "timer-18", timername: "Interacci&oacute;n parejas B2", time: 360, status: "stop", original: 360 },
	{ id: "timer-19", timername: "Interacci&oacute;n tr&iacute;o B2", time: 480, status: "stop", original: 480 },
	{ id: "timer-20", timername: "Preparaci&oacute;n mediaci&oacute;n B2", time: 240, status: "stop", original: 240 },
	{ id: "timer-21", timername: "Mediaci&oacute;n B2", time: 180, status: "stop", original: 180 },
	// Temporizadores C1
	{ id: "timer-22", timername: "Preparación mon&oacute;logo C1<a id='C1'></a>", time: 120, status: "stop", original: 120 },
	{ id: "timer-23", timername: "Mon&oacute;logo C1", time: 180, status: "stop", original: 180 },
	{ id: "timer-24", timername: "Preparación Interacci&oacute;n C1", time: 120, status: "stop", original: 120 },
	{ id: "timer-25", timername: "Interacci&oacute;n parejas C1", time: 360, status: "stop", original: 360 },
	{ id: "timer-26", timername: "Interacci&oacute;n tr&iacute;o C1", time: 480, status: "stop", original: 480 },
	{ id: "timer-27", timername: "Preparaci&oacute;n mediaci&oacute;n C1", time: 240, status: "stop", original: 240 },
	{ id: "timer-28", timername: "Mediaci&oacute;n C1", time: 210, status: "stop", original: 210 },
	// Temporizadores C2
	{ id: "timer-29", timername: "Preparación mon&oacute;logo C2<a id='C2'></a>", time: 120, status: "stop", original: 120 },
	{ id: "timer-30", timername: "Mon&oacute;logo C2", time: 180, status: "stop", original: 180 },
	{ id: "timer-31", timername: "Preparación Interacci&oacute;n C2", time: 120, status: "stop", original: 120 },
	{ id: "timer-32", timername: "Interacci&oacute;n parejas C2", time: 360, status: "stop", original: 360 },
	{ id: "timer-33", timername: "Interacci&oacute;n tr&iacute;o C2", time: 480, status: "stop", original: 480 },
	{ id: "timer-34", timername: "Preparaci&oacute;n mediaci&oacute;n C2", time: 270, status: "stop", original: 270 },
	{ id: "timer-35", timername: "Mediaci&oacute;n C2", time: 240, status: "stop", original: 240 }
	];

function loadSite() {
    let text = "";
    for (var i = 0; i < time_list.length; i++) {
        text += `
      <div class="timer">
        <div class="innerContainer">
          <h4>${time_list[i].timername}</h4>
          <div class="timer-display">
            <span id="timer-${i + 1}"></span>
		  </div>
        </div>
        <div class="timer-controls"><br><br><br><br><br>
          <button class="timerButton" onclick="startButton(${i})" id="start-${i + 1}">Empezar</button>
          <button class="timerButton" onclick="pauseButton(${i})" id="pause-${i + 1}">Pausa</button>
          <button class="timerButton" onclick="stopButton(${i})" id="reset-${i + 1}">Resetear</button><br><br>
		  <button class="timerButtonSmall" onclick="document.location='#arriba'" id="navegar-${i + 1}">A2</button>
		  <button class="timerButtonSmall" onclick="document.location='#B1'" id="navegar-${i + 1}">B1</button>
		  <button class="timerButtonSmall" onclick="document.location='#B2'" id="navegar-${i + 1}">B2</button>
		  <button class="timerButtonSmall" onclick="document.location='#C1'" id="navegar-${i + 1}">C1</button>
		  <button class="timerButtonSmall" onclick="document.location='#C2'" id="navegar-${i + 1}">C2</button>
		  </div>
      </div>
      `
    }
    document.getElementById('timerContainer').innerHTML = text;
}

function startButton(i) {
    time_list[i].status = "running";
}

function pauseButton(i) {
    time_list[i].status = "stop";
}

function stopButton(i) {
    time_list[i].status = "stop";
    time_list[i].time = time_list[i].original;
}

function newTimer(time) {
    time_list.push({ id: "timer-" + (time_list.length + 1), timername: "Temporizador - " + (time_list.length + 1), time: time, status: "stop", original: time });
    loadSite();
}

let timer_main = setInterval(function () {
    for (let i = 0; i < time_list.length; i++) {
        if (time_list[i].status == "running") {
            time_list[i].time -= 1;

        }
        if (time_list[i].time == 0 && time_list[i].status == "running") {
            time_list[i].status = "stop";
			new Audio("./alarma.mp3").play();
			// alert(`¡El tiempo se ha acabado!`);
        }

        // document.getElementById(time_list[i].id).innerHTML = time_list[i].time;
        // display time in mm:ss format
        let minutes = Math.floor(time_list[i].time / 60);
        let seconds = time_list[i].time % 60;
        if (seconds < 10) {
            seconds = "0" + seconds;
        }
        if (minutes < 10) {
            minutes = "0" + minutes;
        }
        try {
            document.getElementById(time_list[i].id).innerHTML = minutes + ":" + seconds;
        } catch (err) {
            console.log(err);
        }


    }
}, 1000);
</script>
</head>
<body onload="loadSite()">
  <h1>Cron&oacute;metros certificaci&oacute;n idiomas<a id="arriba"></a></h1>
  <h2>Convocatoria Asturias 24-25</h2>
  <div id="controls">
    <h2>Enlaces</h2>
    <button class="timerButtonSmall" onclick="document.location='#arriba'" id="navegar-${i + 1}">A2</button>
	<button class="timerButtonSmall" onclick="document.location='#B1'" id="navegar-${i + 1}">B1</button>
	<button class="timerButtonSmall" onclick="document.location='#B2'" id="navegar-${i + 1}">B2</button>
	<button class="timerButtonSmall" onclick="document.location='#C1'" id="navegar-${i + 1}">C1</button>
	<button class="timerButtonSmall" onclick="document.location='#C2'" id="navegar-${i + 1}">C2</button>
    <button class="timerButton" onclick="document.location='#timer-32'" id="navegar-${i + 1}">Mis cronos</button>	
	<button class="timerButton" style="width:250px ;" onclick="newTimer(prompt('¿Cu&aacute;ntos segundos?'))">+ Crono personalizado</button>
	<button class="timerButton" style="width:250px ;" onclick="window.open('intcorta.html', '_self')">Ir a interacci&oacute;n corta</button>
  </div>
  <div id="timerContainer"></div>
  <br>
<p align="center">Desarrollado por <a href="mailto:antoniojjm@educastur.org">antoniojjm@educastur.org</a> a partir de <a href="https://github.com/dejvoss/js-multiple-timer" "target="_blank">JS Multiple Timer by DeOS</a> y <a href="https://freesound.org/people/BarkersPinhead/sounds/274806/" "target="_blank">Alarm Timer Watch coundown by BankersPinhead</a> (CC Attrib. 4.0).</p>
<p align="center">Puedes ajustar el tamaño progresivamente con tu navegador (Control + o bien Control -). Versi&oacute;n en vivo en <a href="http://ajimenez.x10.mx/CerCronos/">http://ajimenez.x10.mx/CerCronos/</a></p>
<p align="center">Puedes descargar <a href=".\CerCronos.zip">la &uacute;ltima versi&oacute;n de esta página</a> para usarla sin conexión. Deber&aacute;s descomprimir el archivo zip a una carpeta y abrir CerCronos.html con cualquier navegador.</p>
<br><br></body>
</html>
