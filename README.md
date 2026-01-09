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
      padding: 10px;
      width: 80%;
      margin: 8px 0;
      font-size: 16px;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      margin-top: 10px;
    }
    .error {
      color: red;
      display: none;
    }
    .contenido {
      display: none;
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

  <p>2️⃣ ¿En qué fecha empezamos a salir? (x/x/xxxx)</p>
  <input id="p2">

  <p>3️⃣ ¿Cuál es el nombre del mejor jugador de pádel del mundo?</p>
  <input id="p3">

  <p>4️⃣ ¿Cómo se llama mi película favorita?</p>
  <input id="p4">

  <p>5️⃣ ¿Destino de nuestro primer viaje juntos?</p>
  <input id="p5">

  <button onclick="verificarPreguntas()">Comprobar respuestas</button>
  <p class="error" id="errorPreguntas">❌ Has fallado alguna… inténtalo otra vez</p>
</div>

<!-- CANCIÓN -->
<div class="box contenido" id="cancion">
  <h2>🎶 Prueba musical</h2>
  <p>Escucha este trocito… 💕</p>

  <audio controls>
    <source src="cancion.mp3" type="audio/mpeg">
    Tu navegador no soporta audio
  </audio>

  <p>¿Cómo se llama la canción?</p>
  <input id="respuestaCancion" placeholder="Nombre de la canción">
  <button onclick="verificarCancion()">Responder</button>
  <p class="error" id="errorCancion">❌ No es esa…</p>
</div>

<!-- FINAL -->
<div class="box contenido" id="final">
  <h1>🎁 ¡Lo has conseguido!</h1>
  <p>Has superado TODAS las pruebas 💖</p>
  <p>Tu regalo te espera… 😏✨</p>
</div>

<script>
  const CLAVE = "rickymorty";

  function comprobar() {
    const input = document.getElementById("password").value;
    if (input === CLAVE) {
      document.getElementById("login").style.display = "none";
      document.getElementById("preguntas").style.display = "block";
    } else {
      document.getElementById("error").style.display = "block";
    }
  }

  function verificarPreguntas() {
    const respuestas = [
      "olesa de bonesvalls",
      "27/09/2019",
      "pablo",
      "regreso al futuro",
      "canarias"
    ];

    const inputs = [
      p1.value, p2.value, p3.value, p4.value, p5.value
    ].map(v => v.toLowerCase().trim());

    for (let i = 0; i < respuestas.length; i++) {
      if (inputs[i] !== respuestas[i]) {
        document.getElementById("errorPreguntas").style.display = "block";
        return;
      }
    }

    document.getElementById("preguntas").style.display = "none";
    document.getElementById("cancion").style.display = "block";
  }

  function verificarCancion() {
    const correcta = "NOMBRE DE LA CANCION"; // 👈 CAMBIA ESTO
    const respuesta = document.getElementById("respuestaCancion").value
      .toLowerCase()
      .trim();

    if (respuesta === correcta.toLowerCase()) {
      document.getElementById("cancion").style.display = "none";
      document.getElementById("final").style.display = "block";
    } else {
      document.getElementById("errorCancion").style.display = "block";
    }
  }
</script>

</body>
</html>
