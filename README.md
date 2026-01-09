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
      max-width: 400px;
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
  <p>Solo alguien muy especial puede continuar 💕</p>
  <input type="password" id="password" placeholder="Contraseña">
  <br>
  <button onclick="comprobar()">Entrar</button>
  <p class="error" id="error">❌ Contraseña incorrecta</p>
</div>

<!-- PREGUNTAS -->
<div class="box contenido" id="preguntas">
  <h2>🧩 Prueba final</h2>

  <p>1️⃣ ¿Dónde fue nuestra primera cita?</p>
  <input id="p1">

  <p>2️⃣ ¿En qué mes empezamos a salir?</p>
  <input id="p2">

  <p>3️⃣ ¿Mi comida favorita?</p>
  <input id="p3">

  <p>4️⃣ ¿Cómo te llamo a veces?</p>
  <input id="p4">

  <p>5️⃣ ¿Ciudad de nuestro mejor recuerdo juntos?</p>
  <input id="p5">

  <button onclick="verificarPreguntas()">Comprobar respuestas</button>
  <p class="error" id="errorPreguntas">❌ Has fallado alguna… inténtalo otra vez</p>
</div>

<!-- FINAL -->
<div class="box contenido" id="final">
  <h1>🎁 ¡Lo has conseguido!</h1>
  <p>Has acertado TODAS las pruebas 💖</p>
  <p>Tu regalo te espera… 😏✨</p>
</div>

<script>
  const CLAVE = "hola"; // contraseña

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
    // RESPUESTAS CORRECTAS (en minúsculas)
    const respuestas = [
      "cine",
      "abril",
      "pizza",
      "cariño",
      "paris"
    ];

    const inputs = [
      document.getElementById("p1").value.toLowerCase().trim(),
      document.getElementById("p2").value.toLowerCase().trim(),
      document.getElementById("p3").value.toLowerCase().trim(),
      document.getElementById("p4").value.toLowerCase().trim(),
      document.getElementById("p5").value.toLowerCase().trim()
    ];

    for (let i = 0; i < respuestas.length; i++) {
      if (inputs[i] !== respuestas[i]) {
        document.getElementById("errorPreguntas").style.display = "block";
        return;
      }
    }

    // Si acierta todas
    document.getElementById("preguntas").style.display = "none";
    document.getElementById("final").style.display = "block";
  }
</script>

</body>
</html>
