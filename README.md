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
      margin: 10px 0;
      font-size: 16px;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
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

<div class="box" id="login">
  <h2>🔐 Acceso secreto</h2>
  <p>Solo alguien muy especial puede continuar 💕</p>
  <p><em>Pista: algo que solo nosotros sabemos</em></p>
  <input type="password" id="password" placeholder="Contraseña">
  <br>
  <button onclick="comprobar()">Entrar</button>
  <p class="error" id="error">❌ Contraseña incorrecta</p>
</div>

<div class="box contenido" id="contenido">
  <h1>🎉 Bienvenida a la misión</h1>
  <p>Has desbloqueado la gincana 💖</p>
  <p>Aquí empiezan las pruebas…</p>
</div>

<script>
  const CLAVE = "hola"; 

  function comprobar() {
    const input = document.getElementById("password").value;
    if (input === CLAVE) {
      document.getElementById("login").style.display = "none";
      document.getElementById("contenido").style.display = "block";
    } else {
      document.getElementById("error").style.display = "block";
    }
  }
</script>

</body>
</html>
