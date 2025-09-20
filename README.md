v<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Juego de clics 🎮</title>
  <style>
    body {
      margin: 0;
      background: #222;
      color: white;
      text-align: center;
      font-family: Arial, sans-serif;
    }
    #game {
      position: relative;
      width: 100%;
      height: 90vh;
      background: #333;
      overflow: hidden;
    }
    #target {
      position: absolute;
      width: 60px;
      height: 60px;
      background: red;
      border-radius: 50%;
      cursor: pointer;
    }
    h1 {
      margin: 10px;
    }
  </style>
</head>
<body>
  <h1>Puntos: <span id="score">0</span></h1>
  <div id="game">
    <div id="target"></div>
  </div>

  <script>
    let target = document.getElementById("target");
    let game = document.getElementById("game");
    let scoreDisplay = document.getElementById("score");
    let score = 0;

    function moverTarget() {
      let x = Math.random() * (game.clientWidth - 60);
      let y = Math.random() * (game.clientHeight - 60);
      target.style.left = x + "px";
      target.style.top = y + "px";
    }

    target.addEventListener("click", () => {
      score++;
      scoreDisplay.textContent = score;
      moverTarget();
    });

    setInterval(moverTarget, 1000); // se mueve cada 1 segundo
    moverTarget();
  </script>
</body>
</html>
