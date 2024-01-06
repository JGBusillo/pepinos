<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 100px;
    }

    #question {
      font-size: 24px;
      margin-bottom: 20px;
    }

    #options {
      display: flex;
      justify-content: center;
    }

    button {
      margin: 0 10px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
  <script>
    function mostrarRespuesta(respuesta) {
      if (respuesta === 'si') {
        document.getElementById('question-container').innerHTML = '<p>"¡Ah, por supuesto que me has perdonado! ¿Cómo podrías resistirte a mi irresistible encanto?"</p>';
      } else if (respuesta === 'no') {
        const button = document.getElementById('no-button');
        const maxX = window.innerWidth - button.clientWidth;
        const maxY = window.innerHeight - button.clientHeight;
        const randomX = Math.floor(Math.random() * maxX);
        const randomY = Math.floor(Math.random() * maxY);
        button.style.position = 'absolute';
        button.style.left = randomX + 'px';
        button.style.top = randomY + 'px';
      }
    }
  </script>
</head>
<body>
  <div id="question-container">
    <p id="question">¿Me perdonas?</p>
    <div id="options">
      <button onclick="mostrarRespuesta('si')">Sí</button>
      <button id="no-button" onclick="mostrarRespuesta('no')">No</button>
    </div>
  </div>
</body>
</html>
