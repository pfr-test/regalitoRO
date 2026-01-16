<!DOCTYPE html>
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
input {
  display: block;
  padding: 10px;
  width: 80%;
  margin: 8px auto;
  font-size: 16px;
}
button {
  display: block;
  padding: 10px 20px;
  font-size: 16px;
  margin: 15px auto 0;
  cursor: pointer;
}
.error {
  color: red;
  display: none;
}
.contenido {
  display: none;
}
.checkbox {
  text-align: left;
  margin: 10px 0;
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
  <input type="password" id="password" placeholder="Contraseña">
  <button onclick="comprobar()">Entrar</button>
  <p class="error" id="error">❌ Contraseña incorrecta</p>
</div>

<!-- PREGUNTAS -->
<div class="box contenido" id="preguntas">
  <p>¿Dónde fue nuestro primer beso?</p><input id="p1">
  <p>¿Fecha que empezamos a salir?</p><input id="p2">
  <p>Mejor jugador de pádel del mundo</p><input id="p3">
  <p>Mi peli favorita</p><input id="p4">
  <p>Primer viaje juntos</p><input id="p5">
  <button onclick="verificarPreguntas()">Comprobar</button>
  <p class="error" id="errorPreguntas">❌ Has fallado alguna</p>
</div>

<!-- CANCIÓN -->
<div class="box contenido" id="cancion">
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
  <h2>🗝️ Código del amor</h2>
  <p>Ordena de MÁS ANTIGUO a MÁS RECIENTE</p>
  <p>1️⃣ Primer viaje<br>2️⃣ Primer beso<br>3️⃣ Empezamos a salir</p>
  <input id="codigoRespuesta" placeholder="Ej: 2-3-1">
  <button onclick="verificarCodigo()">Comprobar</button>
  <p class="error" id="errorCodigo">❌ No es correcto</p>
</div>

<!-- VERDADERO / FALSO -->
<div class="box contenido" id="vf">
  <h2>✔️ Verdadero o Falso</h2>

  <p>Yo me enamoré antes que tú</p>
  <select id="vf1"><option value="">---</option><option>V</option><option>F</option></select>

  <p>Nuestro primer viaje fue improvisado</p>
  <select id="vf2"><option value="">---</option><option>V</option><option>F</option></select>

  <p>Ese día llovía</p>
  <select id="vf3"><option value="">---</option><option>V</option><option>F</option></select>

  <button onclick="verificarVF()">Comprobar</button>
  <p class="error" id="errorVF">❌ Alguna no es correcta</p>
</div>

<!-- RETOS -->
<div class="box contenido" id="retos">
  <div class="checkbox"><label><input type="checkbox" id="r1"> Darme de comer</label></div>
  <div class="checkbox"><label><input type="checkbox" id="r2"> Beso con sentimiento</label></div>
  <div class="checkbox"><label><input type="checkbox" id="r3"> 5 flexiones</label></div>
  <button onclick="verificarRetos()">Hecho</button>
  <p class="error" id="errorRetos">❌ Faltan retos</p>
</div>

<!-- ELECCIÓN -->
<div class="box contenido" id="eleccion">
  <button onclick="fallo(1)">🎁 1</button>
  <button onclick="fallo(2)">🎁 2</button>
  <button onclick="acierto()">🎁 3</button>
</div>

<!-- FALLO -->
<div class="box contenido" id="fallo">
  <img id="fotoFallo">
  <p id="mensajeFallo"></p>
  <button onclick="volverIntentar()">Volver</button>
</div>

<!-- ACIERTO -->
<div class="box contenido" id="acierto">
  <h2>🎉 ¡Has ganado!</h2>
  <p>RESERVA ESA FECHA 💕</p>
</div>

<script>
const CLAVE = "rickymorty";

function comprobar(){
  if(password.value === CLAVE){
    login.style.display="none";
    preguntas.style.display="block";
  } else error.style.display="block";
}

function verificarPreguntas(){
  const ok=["olesa de bonesvalls","27/09/2019","pablo","regreso al futuro","canarias"];
  const v=[p1,p2,p3,p4,p5].map(i=>i.value.toLowerCase().trim());
  if(ok.every((r,i)=>r===v[i])){
    preguntas.style.display="none";
    cancion.style.display="block";
  } else errorPreguntas.style.display="block";
}

function verificarCancion(){
  if(respuestaCancion.value.toLowerCase()==="malaikah"){
    cancion.style.display="none";
    codigoAmor.style.display="block";
  } else errorCancion.style.display="block";
}

function verificarCodigo(){
  if(codigoRespuesta.value.trim()==="2-3-1"){
    codigoAmor.style.display="none";
    vf.style.display="block";
  } else errorCodigo.style.display="block";
}

function verificarVF(){
  if(vf1.value==="V" && vf2.value==="F" && vf3.value==="V"){
    vf.style.display="none";
    retos.style.display="block";
  } else errorVF.style.display="block";
}

function verificarRetos(){
  if(r1.checked&&r2.checked&&r3.checked){
    retos.style.display="none";
    eleccion.style.display="block";
  } else errorRetos.style.display="block";
}

function fallo(n){
  eleccion.style.display="none";
  fallo.style.display="block";
  fotoFallo.src=`fallo${n}.jpg`;
  mensajeFallo.textContent="No era ese 😏";
}
function acierto(){
  eleccion.style.display="none";
  acierto.style.display="block";
}
function volverIntentar(){
  fallo.style.display="none";
  eleccion.style.display="block";
}
</script>
</body>
</html>
