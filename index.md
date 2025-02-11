<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>¿Quieres pasar San Valentín conmigo?</title>
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.3.2"></script>
  <style>
    body {
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      text-align: center;
      padding: 20px;
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      overflow: hidden;
    }
    h1 {
      color: #e91e63;
      font-size: 2em;
      margin-bottom: 20px;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
    }
    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
    }
    button {
      padding: 10px 20px;
      font-size: 1em;
      border: none;
      border-radius: 25px;
      cursor: pointer;
      transition: transform 0.3s ease, background-color 0.2s, box-shadow 0.2s;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }
    #si {
      background: linear-gradient(135deg, #4caf50, #81c784);
      color: white;
    }
    #no {
      background: linear-gradient(135deg, #f44336, #e57373);
      color: white;
    }
    button:hover {
      transform: scale(1.1);
      box-shadow: 0 6px 8px rgba(0, 0, 0, 0.2);
    }
    #image-container, #message {
      margin-top: 20px;
    }
    #message {
      font-size: 1.5em;
      color: #e91e63;
      font-weight: bold;
      display: none;
    }
    img {
      border-radius: 15px;
      max-width: 90%;
      height: auto;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }
  </style>
</head>
<body>
  <h1>¿Quieres pasar San Valentín conmigo?</h1>
  <div class="buttons">
    <button id="si">SÍ</button>
    <button id="no">NO</button>
  </div>
  <div id="image-container"></div>
  <div id="message">Yo también te amo ❤️</div>

  <script>
    document.addEventListener("DOMContentLoaded", function() {
      const siButton = document.getElementById('si');
      const noButton = document.getElementById('no');
      const imageContainer = document.getElementById('image-container');
      const message = document.getElementById('message');

      function confirmarAmor(event) {
        event.preventDefault();
        setTimeout(() => {
          confetti({ particleCount: 100, spread: 70, origin: { y: 0.6 } });
          imageContainer.innerHTML = '<img src="https://media.tenor.com/xvb9NlgJBS4AAAAM/piggy-back-ride.gif" alt="Cute Photo">';
          message.style.display = 'block';
        }, 100);
      }

      function reducirNo(event) {
        event.preventDefault();
        setTimeout(() => {
          noButton.style.transform = `scale(0.8)`;
          siButton.style.transform = `scale(1.2)`;
        }, 100);
      }

      siButton.addEventListener('click', confirmarAmor, false);
      siButton.addEventListener('touchend', confirmarAmor, false);
      noButton.addEventListener('click', reducirNo, false);
      noButton.addEventListener('touchend', reducirNo, false);
    });
  </script>
</body>
</html>
