---
draft: false
title: Jeu de la vie et automates cellulaires
---
%%

<!DOCTYPE html>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Conway's Game of Life</title>
    <style>
        canvas { border: 1px solid black; background-color: black; }
        button { margin: 5px; padding: 10px; font-size: 16px; }
        .button-container { display: flex; justify-content: center; margin-top: 10px; flex-wrap: wrap; }
        .button-container button { display: flex; align-items: center; gap: 5px; }
    </style>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" rel="stylesheet">
</head>
<body>
    <h1 style="color:white; text-align:center;">Conway's Game of Life</h1>
    <canvas id="gameCanvas" width="700" height="500" style="display:block; margin: 0 auto;"></canvas>
    <div class="button-container">
        <button onclick="step()"><i class="fas fa-forward"></i> Play Step by Step</button>
        <button onclick="play()"><i class="fas fa-play"></i> Play</button>
        <button onclick="pause()"><i class="fas fa-pause"></i> Pause</button>
        <button onclick="reset()"><i class="fas fa-redo"></i> Reset</button>
        <button onclick="randomize()"><i class="fas fa-random"></i> Random</button>
        <button onclick="placePattern()"><i class="fas fa-shapes"></i> Pattern</button>
    </div>
    <script data-preval>
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        const gridWidth = 70;
        const gridHeight = 50;
        const cellSize = canvas.width / gridWidth;
        let grid = Array.from({ length: gridHeight }, () => Array(gridWidth).fill(0));
        let playing = false;
        let interval;
        let patternIndex = 0;

        const patterns = [
            // Gosper Glider Gun
            { name: 'Gosper Glider Gun', cells: [
                [1, 5], [1, 6], [2, 5], [2, 6],
                [11, 5], [11, 6], [11, 7],
                [12, 4], [12, 8],
                [13, 3], [13, 9],
                [14, 3], [14, 9],
                [15, 6],
                [16, 4], [16, 8],
                [17, 5], [17, 6], [17, 7],
                [18, 6],
                [21, 3], [21, 4], [21, 5],
                [22, 3], [22, 4], [22, 5],
                [23, 2], [23, 6],
                [25, 1], [25, 2], [25, 6], [25, 7],
                [35, 3], [35, 4], [36, 3], [36, 4]
            ]}
        ];

        canvas.addEventListener('click', (e) => {
            const x = Math.floor(e.offsetX / cellSize);
            const y = Math.floor(e.offsetY / cellSize);
            grid[y][x] = grid[y][x] ? 0 : 1;
            drawGrid();
        });

        function drawGrid() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for (let y = 0; y < gridHeight; y++) {
                for (let x = 0; x < gridWidth; x++) {
                    ctx.fillStyle = grid[y][x] ? 'white' : 'black';
                    ctx.fillRect(x * cellSize, y * cellSize, cellSize, cellSize);
                    ctx.strokeStyle = '#555';
                    ctx.lineWidth = 0.5;
                    ctx.strokeRect(x * cellSize, y * cellSize, cellSize, cellSize);
                }
            }
        }

        function placePattern() {
            reset();
            const pattern = patterns[patternIndex % patterns.length];
            const offsetX = 10, offsetY = 10;
            pattern.cells.forEach(([x, y]) => {
                if (y + offsetY < gridHeight && x + offsetX < gridWidth) {
                    grid[y + offsetY][x + offsetX] = 1;
                }
            });
            patternIndex++;
            drawGrid();
        }

        function step() {...}
        function play() {...}
        function pause() {...}
        function reset() {...}
        function randomize() {...}

        drawGrid();
    </script>
</body>
</html>

 %%


<div style="text-align: center;">
<iframe src="/gameoflife.html" width="750" height="600" style="border: none;"`></iframe>
</div>


## Quelques liens

- On peut trouver beaucoup d'excellentes vidéos sur le sujet par ScienceEtonnante :
	- Sur le [jeu de la vie de Conway](https://www.youtube.com/watch?v=S-W0NX97DB0)
	- Sur [LENIA](https://www.youtube.com/watch?v=PlzV4aJ7iMI), une automate cellulaire plus complexe.
	- Une [playlist entière](https://www.youtube.com/playlist?list=PLxzM9a5lhAukJ5auZBMVMx6UyA_N9j-wa) sur des thèmes liés aux automates cellulaires.
- Une vidéo d'[Ego](https://www.youtube.com/watch?v=eMn43As24Bo) sur le jeu de la vie de Conway.
- [Golly](https://golly.sourceforge.io/), une application gratuite et open-source permettant de manipuler le jeu de la vie de Conway, ainsi qu'une pléiade d'autres automates cellulaires.