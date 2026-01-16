<html lang="es">
<head>
<meta charset="UTF-8">
<title>Misión Secreta 💖</title>
<style>
body {
  font-family: Arial, sans-serif;
  background: #fff0f5;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  text-align: center;
}
.box {
  background: white;
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0 0 15px rgba(0,0,0,0.1);
  max-width: 420px;
  width: 100%;
}
input[type="text"], input[type="password"] {
  display: block;
  padding: 10px;
  width: 80%;
  margin: 8px auto;
  font-size: 16px;
}
.checkbox {
  text-align: left;
  margin: 10px 0;
}
button {
  display: block;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  margin: 15px auto 0 auto;
}
.error {
  color: red;
  display: none;
}
.contenido {
  display: none;
}
img {
  width: 100%;
  border-radius: 12px;
  margin-top: 10px;
}
</style>
</head>
<body>

<!-- LOGIN -->
<div class="box" id="login">
  <h2>🔐 Acceso secreto</h2>
  <p>Pon la contraseña correcta</p>
  <p><em>Pista: Serie que finjiste verte para enamorar a este chico joven y guapo</em></p>
  <input type="password" id="password" placeholder="Contraseña">
  <br>
  <button onclick="comprobar()">Entrar</button>
  <p class="error" id="error">❌ Contraseña incorrecta</p>
</div>

<!-- PREGUNTAS -->
<div class="box contenido" id="preguntas">
  <h2>🧩 Primera prueba</h2>
  <p>1️⃣ ¿Dónde fue nuestro primer beso?</p>
  <input id="p1">
  <p>2️⃣ ¿En qué fecha empezamos a salir?</p>
  <input id="p2">
  <p>3️⃣ ¿Caul es el nombre del mejor jugador de pádel del mundo?</p>
  <input id="p3">
  <p>4️⃣ ¿Mi película favorita?</p>
  <input id="p4">
  <p>5️⃣ ¿Nuestro primer viaje juntos?</p>
  <input id="p5">
  <button onclick="verificarPreguntas()">Comprobar</button>
  <p class="error" id="errorPreguntas">❌ Has fallado alguna</p>
</div>

<!-- CANCIÓN -->
<div class="box contenido" id="cancion">
  <h2>🎶 Prueba musical</h2>
  <audio controls>
    <source src="cancion.mp3" type="audio/mpeg">
  </audio>
  <p>¿Cómo se llama la canción?</p>
  <input id="respuestaCancion">
  <button onclick="verificarCancion()">Responder</button>
  <p class="error" id="errorCancion">❌ No es esa</p>
</div>
<!-- CÓDIGO DEL AMOR -->
<div class="box contenido" id="codigoAmor">
  <h2>🗝️Ordena correctamente</h2>
  <p>Ordena de MÁS ANTIGUO a MÁS RECIENTE</p>
  <p>1️⃣ Primer spa juntos <br>2️⃣ Vamos a ver a BadBo<br>3️⃣ Primer viaje juntos <br>4️⃣ La munch y la Mar se conocen</p>
  <input id="codigoRespuesta" placeholder="Ej: 1-2-3-4">
  <button onclick="verificarCodigo()">Comprobar</button>
  <p class="error" id="errorCodigo">❌ No es correcto</p>
</div>

<!-- VERDADERO / FALSO -->
<div class="box contenido" id="vf">
  <h2>✔️ Verdadero o Falso</h2>

  <p>Yo te pedí salir a ti (definitivamente)</p>
  <select id="vf1"><option value="">---</option><option>V</option><option>F</option></select>

  <p>Nuestro primer concierto fue Funzo y Babyloud</p>
  <select id="vf2"><option value="">---</option><option>V</option><option>F</option></select>

  <p>En nuestra primera cena en tu casa tu madre hizo tortilla</p>
  <select id="vf3"><option value="">---</option><option>V</option><option>F</option></select>

  <p>Nuestra primera vez que quedamos fuimos al cine</p>
  <select id="vf4"><option value="">---</option><option>V</option><option>F</option></select>

  <button onclick="verificarVF()">Comprobar</button>
  <p class="error" id="errorVF">❌ Alguna no es correcta</p>
</div>
<!-- RETOS CHECKBOX -->
<div class="box contenido" id="retos">
  <h2>✅ Última prueba</h2>
  <p>Completa TODOS los retos:</p>
  <div class="checkbox">
    <label><input type="checkbox" id="r1"> Darle algo de comer a tu querido novio</label>
  </div>
  <div class="checkbox">
    <label><input type="checkbox" id="r2"> Darle un beso (con sentimiento) a todas las personas de la sala</label>
  </div>
  <div class="checkbox">
    <label><input type="checkbox" id="r3"> Hacer 5 flexiones</label>
  </div>
  <button onclick="verificarRetos()">Hecho</button>
  <p class="error" id="errorRetos">❌ Faltan retos por cumplir</p>
</div>

<!-- ELECCIÓN DEL REGALO -->
<div class="box contenido" id="eleccion">
  <h2>🎁 Elige tu regalo</h2>
  <p>Solo uno es el correcto… elige sabiamente 😏</p>
  <button onclick="fallo(1)">🎁 Regalo 1</button>
  <button onclick="fallo(2)">🎁 Regalo 2</button>
  <button onclick="fallo(3)">🎁 Regalo 3</button>
  <button onclick="fallo(4)">🎁 Regalo 4</button>
  <button onclick="fallo(5)">🎁 Regalo 5</button>
  <button onclick="fallo(6)">🎁 Regalo 6</button>
  <button onclick="acierto()">🎁 Regalo 7</button>
  <button onclick="fallo(8)">🎁 Regalo 8</button>
</div>

<!-- RESULTADO FALLOS -->
<div class="box contenido" id="fallo">
  <h2>❌ Casi…</h2>
  <img id="fotoFallo">
  <p id="mensajeFallo"></p>
  <button onclick="volverIntentar()">Volver a intentar</button>
</div>

<!-- RESULTADO ACIERTO -->
<div class="box contenido" id="acierto">
  <h2>🎉 ¡Has acertado!</h2>
  <img src="acierto.jpg">
  <p>Tu regalo es… <strong>RESERVA ESA FECHA, QUE NOS VAMOS A VER AL JUAN DAVILA</strong></p>
</div>

<script>
const CLAVE = "rickymorty";

// Elementos
const loginDiv = document.getElementById("login");
const preguntasDiv = document.getElementById("preguntas");
const cancionDiv = document.getElementById("cancion");
const codigoDiv = document.getElementById("codigoAmor");
const vfDiv = document.getElementById("vf");
const retosDiv = document.getElementById("retos");
const eleccionDiv = document.getElementById("eleccion");
const falloDiv = document.getElementById("fallo");
const aciertoDiv = document.getElementById("acierto");

const fotoFallo = document.getElementById("fotoFallo");
const mensajeFallo = document.getElementById("mensajeFallo");

const password = document.getElementById("password");
const p1 = document.getElementById("p1");
const p2 = document.getElementById("p2");
const p3 = document.getElementById("p3");
const p4 = document.getElementById("p4");
const p5 = document.getElementById("p5");

const respuestaCancion = document.getElementById("respuestaCancion");
const codigoRespuesta = document.getElementById("codigoRespuesta");

const vf1 = document.getElementById("vf1");
const vf2 = document.getElementById("vf2");
const vf3 = document.getElementById("vf3");

const r1 = document.getElementById("r1");
const r2 = document.getElementById("r2");
const r3 = document.getElementById("r3");

const error = document.getElementById("error");
const errorPreguntas = document.getElementById("errorPreguntas");
const errorCancion = document.getElementById("errorCancion");
const errorCodigo = document.getElementById("errorCodigo");
const errorVF = document.getElementById("errorVF");
const errorRetos = document.getElementById("errorRetos");

// LOGIN
function comprobar() {
  if (password.value === CLAVE) {
    loginDiv.style.display = "none";
    preguntasDiv.style.display = "block";
  } else {
    error.style.display = "block";
  }
}

// PREGUNTAS
function verificarPreguntas() {
  const respuestas = [
    "olesa de bonesvalls",
    "27/09/2019",
    "pablo",
    "regreso al futuro",
    "canarias"
  ];
  const inputs = [p1,p2,p3,p4,p5].map(i => i.value.toLowerCase().trim());

  for (let i = 0; i < respuestas.length; i++) {
    if (inputs[i] !== respuestas[i]) {
      errorPreguntas.style.display = "block";
      return;
    }
  }
  preguntasDiv.style.display = "none";
  cancionDiv.style.display = "block";
}

// CANCIÓN
function verificarCancion() {
  if (respuestaCancion.value.toLowerCase().trim() === "malaikah") {
    cancionDiv.style.display = "none";
    codigoDiv.style.display = "block";
  } else {
    errorCancion.style.display = "block";
  }
}

// CÓDIGO DEL AMOR
function verificarCodigo() {
  if (codigoRespuesta.value.trim() === "4-1-3-2") {
    codigoDiv.style.display = "none";
    vfDiv.style.display = "block";
  } else {
    errorCodigo.style.display = "block";
  }
}

// VERDADERO / FALSO
function verificarVF() {
  if (vf1.value === "F" && vf2.value === "V" && vf3.value === "F" && vf4.value === "F") {
    vfDiv.style.display = "none";
    retosDiv.style.display = "block";
  } else {
    errorVF.style.display = "block";
  }
}

// RETOS
function verificarRetos() {
  if (r1.checked && r2.checked && r3.checked) {
    retosDiv.style.display = "none";
    eleccionDiv.style.display = "block";
  } else {
    errorRetos.style.display = "block";
  }
}

// REGALOS
function fallo(num) {
  eleccionDiv.style.display = "none";
  falloDiv.style.display = "block";
  fotoFallo.src = `fallo${num}.jpg`;
  mensajeFallo.textContent = "No es ese… pero vaya dos pivones 💕";
}

function acierto() {
  eleccionDiv.style.display = "none";
  aciertoDiv.style.display = "block";
}

function volverIntentar() {
  falloDiv.style.display = "none";
  eleccionDiv.style.display = "block";
}
</script>
</body>
</html>
