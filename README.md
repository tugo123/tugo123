- 👋 Hi, I’m @tugo123
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
<!DOCTYPE html>
<html>
<head>
  <title>Visualización de Datos</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 50px;
    }

    h1 {
      margin-bottom: 20px;
    }

    .data-container {
      display: flex;
      justify-content: space-around;
      margin-top: 20px;
    }

    .data-box {
      border: 1px solid #ccc;
      padding: 20px;
      width: 200px;
    }
  </style>
</head>
<body>
  <h1>Visualización de Datos</h1>
  <div class="data-container">
    <div class="data-box">
      <h2>Voltaje</h2>
      <p id="voltaje"></p>
    </div>
    <div class="data-box">
      <h2>Corriente</h2>
      <p id="corriente"></p>
    </div>
    <div class="data-box">
      <h2>Lux</h2>
      <p id="lux"></p>
    </div>
    <div class="data-box">
      <h2>Radiación Solar</h2>
      <p id="radiacion-solar"></p>
    </div>
  </div>

  <script>
    // Función para obtener los datos desde el servidor y mostrarlos en la página
    function obtenerDatos() {
      fetch('/datos')
        .then(response => response.json())
        .then(data => {
          document.getElementById('voltaje').innerText = data.voltaje + ' V';
          document.getElementById('corriente').innerText = data.corriente + ' mA';
          document.getElementById('lux').innerText = data.lux;
          document.getElementById('radiacion-solar').innerText = data.radiacionSolar + ' W/m²';
        })
        .catch(error => {
          console.error('Error al obtener los datos:', error);
        });
    }

    // Obtener los datos cada 5 segundos (ajustar el intervalo según lo deseado)
    setInterval(obtenerDatos, 5000);

    // Obtener los datos por primera vez al cargar la página
    obtenerDatos();
  </script>
</body>
</html>
<!---
tugo123/tugo123 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
