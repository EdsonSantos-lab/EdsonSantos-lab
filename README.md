<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EdsonSantos - GitHub</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            text-align: center;
        }
        .container {
            max-width: 800px;
            margin: 50px auto;
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            color: #333;
        }
        .python-logo {
            width: 100px;
            margin-top: 20px;
        }
        .tech {
            font-size: 18px;
            color: #555;
            margin-top: 10px;
        }
        .game-container {
            margin-top: 20px;
        }
        canvas {
            border: 2px solid #000;
            background-color: #87CEEB;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Bem-vindo ao meu GitHub!</h2>
        <p>Esse é o meu espaço para compartilhar projetos e conhecimento.</p>
        <img class="python-logo" src="https://upload.wikimedia.org/wikipedia/commons/c/c3/Python-logo-notext.svg" alt="Logo Python">
        <p class="tech">Tecnologia principal: <strong>Python</strong></p>
        <div class="game-container">
            <canvas id="gameCanvas" width="400" height="200"></canvas>
        </div>
    </div>
    <script>
        const canvas = document.getElementById("gameCanvas");
        const ctx = canvas.getContext("2d");
        
        let mario = {
            x: 50,
            y: 150,
            width: 20,
            height: 20,
            color: "red",
            speed: 2
        };
        
        function drawMario() {
            ctx.fillStyle = mario.color;
            ctx.fillRect(mario.x, mario.y, mario.width, mario.height);
        }
        
        function updateGame() {
            mario.x += mario.speed;
            if (mario.x > canvas.width) {
                mario.x = -mario.width;
            }
        }
        
        function gameLoop() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            drawMario();
            updateGame();
            requestAnimationFrame(gameLoop);
        }
        
        gameLoop();
    </script>
</body>
</html>
