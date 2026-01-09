
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
  </style>
</head>
<body>

<!-- LOGIN -->
<div class="box" id="login">
  <h2>🔐 Acceso secreto</h2>
  <p>Pon la contraseña correcta TGGGGGGGGGG</p>
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

  <p>3️⃣ ¿Quién es el mejor jugador de pádel del mundo?</p>
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

<!-- FINAL -->
<div class="box contenido" id="final">
  <h1>🎁 ¡Lo has conseguido!</h1>
  <p>Ahora sí… tu regalo te espera 😏💖</p>
</div>

<script>
  const CLAVE = "rickymorty";

  function comprobar() {
    if (password.value === CLAVE) {
      login.style.display = "none";
      preguntas.style.display = "block";
    } else {
      error.style.display = "block";
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

    const inputs = [p1,p2,p3,p4,p5].map(i => i.value.toLowerCase().trim());

    for (let i = 0; i < respuestas.length; i++) {
      if (inputs[i] !== respuestas[i]) {
        errorPreguntas.style.display = "block";
        return;
      }
    }

    preguntas.style.display = "none";
    cancion.style.display = "block";
  }

  function verificarCancion() {
    const correcta = "malaikah";
    if (respuestaCancion.value.toLowerCase().trim() === correcta.toLowerCase()) {
      cancion.style.display = "none";
      retos.style.display = "block";
    } else {
      errorCancion.style.display = "block";
    }
  }

  function verificarRetos() {
    if (r1.checked && r2.checked && r3.checked) {
      retos.style.display = "none";
      final.style.display = "block";
    } else {
      errorRetos.style.display = "block";
    }
  }
</script>

</body>
</html>
