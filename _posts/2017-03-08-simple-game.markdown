---
title: break-out-game
layout: page
---
Building this simple BreakOut game followed by nice MDN instructions, the game is dead-simple but somehow help me to understand some canvas basics and simple UI interactions.


<html>
<head>
  <meta charset="utf-8"/>
  <title>2D Breakout Game</title>
  <style>
    .start-btn {
      display: flex;
      justify-content: center;
    }
    * { padding: 0; margin: 0; }
    canvas {  background: Bisque;
              display: block;
              margin: 0 auto;
            }
    @media screen and (max-width: 600px) {
    canvas {
      width: 400px;
      height: 250px;
      }
  }
  </style>
</head>
<body>
<div class="start-btn">
<input type="button" value="Start the Game" class="btn" />
</div>
<canvas id="gameCanvas" width="600" height="400"></canvas>

<script src="/assets/js/game.js">
</script>
</body>
