<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Labirinto Simples</title>
  <style>
    body { background: #eee; display: flex; justify-content: center; padding: 20px; font-family: Arial; }
    canvas { background: white; border: 2px solid black; }
  </style>
</head>
<body>
  <canvas id="game" width="400" height="400"></canvas>

  <script>
    const canvas = document.getElementById("game");
    const ctx = canvas.getContext("2d");

    // Labirinto simples (0 = caminho | 1 = parede | 2 = saída)
    const map = [
      [1,1,1,1,1,1,1,1,1,1],
      [1,0,0,0,1,0,0,0,0,1],
      [1,0,1,0,1,0,1,1,0,1],
      [1,0,1,0,0,0,0,1,0,1],
      [1,0,1,1,1,1,0,1,0,1],
      [1,0,0,0,0,1,0,1,0,1],
      [1,1,1,1,0,1,0,1,0,1],
      [1,0,0,0,0,0,0,0,0,1],
      [1,0,1,1,1,1,1,1,2,1],
      [1,1,1,1,1,1,1,1,1,1]
    ];

    const tile = 40;

    let player = { x: 1, y: 1 };

    function draw() {
      ctx.clearRect(0, 0, 400, 400);

      for (let y = 0; y < 10; y++) {
        for (let x = 0; x < 10; x++) {
          if (map[y][x] === 1) {
            ctx.fillStyle = "black";
          } else if (map[y][x] === 2) {
            ctx.fillStyle = "green";
          } else {
            ctx.fillStyle = "white";
          }
          ctx.fillRect(x * tile, y * tile, tile, tile);
        }
      }

      // jogador
      ctx.fillStyle = "red";
      ctx.fillRect(player.x * tile, player.y * tile, tile, tile);
    }

    function move(dx, dy) {
      let nx = player.x + dx;
      let ny = player.y + dy;

      if (map[ny][nx] !== 1) {
        player.x = nx;
        player.y = ny;

        // chegou ao final
        if (map[ny][nx] === 2) {
          alert("Você venceu!");
          player = { x: 1, y: 1 };
        }
      }
      draw();
    }

    document.addEventListener("keydown", (e) => {
      if (e.key === "ArrowUp" || e.key === "w") move(0, -1);
      if (e.key === "ArrowDown" || e.key === "s") move(0, 1);
      if (e.key === "ArrowLeft" || e.key === "a") move(-1, 0);
      if (e.key === "ArrowRight" || e.key === "d") move(1, 0);
    });

    draw();
  </script>
</body>
</html>
