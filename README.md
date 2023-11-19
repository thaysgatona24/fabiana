# fabiana
HTML
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Alura MIDI</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@500;600&display=swap" rel="stylesheet">

    <link rel="icon" type="image/png" href="images/bateria.png">
    <link rel="stylesheet" href="css/reset.css">
    <link rel="stylesheet" href="css/estilos.css">

</head>
<body>

    <h1>Alura Midi</h1>

    <section class="teclado">
        <button class="tecla tecla_pom">Pom</button>
        <button class="tecla tecla_clap">Clap</button>
        <button class="tecla tecla_tim">Tim</button>

        <button class="tecla tecla_puff">Puff</button>
        <button class="tecla tecla_splash">Splash</button>
        <button class="tecla tecla_toim">Toim</button>

        <button class="tecla tecla_psh">Psh</button>
        <button class="tecla tecla_tic">Tic</button>
        <button class="tecla tecla_tom">Tom</button>
    </section>

    <audio src="sounds/keyq.wav" id="som_tecla_pom"></audio>
    <audio src="sounds/keyw.wav" id="som_tecla_clap"></audio>
    <audio src="sounds/keye.wav" id="som_tecla_tim"></audio>
    <audio src="sounds/keya.wav" id="som_tecla_puff"></audio>
    <audio src="sounds/keys.wav" id="som_tecla_splash"></audio>
    <audio src="sounds/keyd.wav" id="som_tecla_toim"></audio>
    <audio src="sounds/keyz.wav" id="som_tecla_psh"></audio>
    <audio src="sounds/keyx.wav" id="som_tecla_tic"></audio>
    <audio src="sounds/keyc.wav" id="som_tecla_tom"></audio>

    <script src="main.js"></script>

</body>
</html>



CSS
:root {
  --cinza: #aaa;
  --vermelha: #e93d50;
  --vermelha-escura: #af303f;
  --branca: #fff;
  --luz: rgb(229, 255, 0);
}

body {
  align-items: center;
  background: linear-gradient(45deg, #a7cfdf 0%,#23538a 100%);
  display: flex;
  justify-content: center;
  flex-direction: column;
  font-family: 'Montserrat', sans-serif;
  min-height: 100vh;
}

h1 {
  color: var(--branca);
  margin-bottom: 20px;
  font-size: 2rem;
}

.teclado {
  background: linear-gradient(to bottom, #eeeeee 0%,#cccccc 100%);
  box-shadow: 6px 8px 0 6px #666, 10px 10px 10px #000;
  border-radius: 30px;
  display: grid;
  gap: 10px;
  grid-template-columns: repeat(3, 1fr);
  padding: 10px;
}

.tecla {
  background-color: var(--branca);
  border-radius: 30px;
  box-shadow: 3px 3px 0 var(--cinza);
  color: var(--vermelha);
  cursor: pointer;
  height: 120px;
  font-size: 1.75em;
  font-weight: bold;
  line-height: 120px;
  text-align: center;
  width: 120px;
}

.tecla.ativa,
.tecla:active {
  background-color: var(--vermelha);
  border: 4px solid  var(--vermelha);
  box-shadow: 3px 3px 0 var(--vermelha-escura) inset;
  color: var(--branca);
  outline: none;
}

.tecla.focus,
.tecla:focus {
  outline: none;
  box-shadow: 1px 1px 10px var(--luz);
}

.tecla.ativa:focus,
.tecla:active:focus {
  box-shadow: 3px 3px 0 var(--vermelha-escura) inset, 1px 1px 10px var(--luz);
}


reset.css 

* {
	box-sizing: border-box;
}

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}

article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}

a {
	color: inherit;
	text-decoration: none;
}

img {
	width: inherit;
}

button {
	font-family: inherit;
	font-size: inherit;
	color: inherit;
	font-weight: inherit;
	padding: 0;
	border: none;
	background-color: unset;
}

input {
	border: none;
	color: inherit;
	font-size: inherit;
	font-weight: inherit;
	font-family: inherit;
}

textarea {
	border: none;
	color: inherit;
	font-size: inherit;
	font-weight: inherit;
	font-family: inherit;
}

select {
	border: none;
	color: inherit;
	font-size: inherit;
	font-weight: inherit;
	font-family: inherit;
}


Main.js 

function tocaSom (seletorAudio) {
    const elemento = document.querySelector(seletorAudio);

    if (elemento && elemento.localName === 'audio') {
        elemento.play();
    }
    else {
        //alert('Elemento não encontrado');
        console.log('Elemento não encontrado ou seletor inválido');
    }

}

const listaDeTeclas = document.querySelectorAll('.tecla');

//para
for (let contador = 0; contador < listaDeTeclas.length; contador++) {

    const tecla = listaDeTeclas[contador];
    const instrumento = tecla.classList[1];
    const idAudio = `#som_${instrumento}`; //template string

    tecla.onclick = function () {
        tocaSom(idAudio);
    }

    tecla.onkeydown = function (evento) {

        if (evento.code === 'Space' || evento.code === 'Enter') {
            tecla.classList.add('ativa');
        }

    }

    tecla.onkeyup = function () {
        tecla.classList.remove('ativa');
    }

}

imagem e sons no alura
https://github.com/alura-cursos/aluramidi-curso/tree/aula5/sounds 
https://github.com/alura-cursos/aluramidi-curso/tree/aula5/images

