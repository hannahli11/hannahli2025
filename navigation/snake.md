---
layout: page
title: Snake
description: Snake Game
permalink: /snake/

---
{% include nav/home.html %}

Future home of snake game

<style>
body.light-theme {
  background-color: white;
  color: black;
}
body.dark-theme {
  background-color: #333;
  color: white;
}
body.blue-theme {
  background-color: #AEC6CF;
  color: white;
}
body.red-theme {
  background-color: #FDFD96;
  color: white;
}
body.green-theme {
  background-color: #C3B1E1;
  color: white;
}
body.grey-theme {
  background-color: #aaa;
  color: white;
}
/* Center the canvas and buttons */
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
canvas {
  border: 1px solid #000;
  background-color: Orchid;
  margin-bottom: 10px; /* Add spacing between canvas and buttons */
}
/* Adjust the button-container */
.button-container {
  text-align: center;
}
.button-container button {
  padding: 10px 20px;
  margin: 5px;
  background-color: Thistle;
  color: Purple;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
.button-container button:hover {
  background-color: #FFC0CB;
}
#game-over {
  font-size: 2em;
  color: Purple;
  text-align: center;
  display: none;
}
</style>
<h1 id="game-over">Game Over!</h1>
<div class="container">
  <canvas id="gameCanvas" width="400" height="400"></canvas>
  <!-- Buttons for controlling the game -->
  <div class="button-container">
    <button id="slow-btn">Slow Mode</button>
    <button id="fast-btn">Fast Mode</button>
    <button id="wall-btn">Wall On/Off</button>
    <button id="theme-btn">Switch Theme</button>
  </div>
</div>
<script>
const canvas = document.getElementById("gameCanvas");
const ctx = canvas.getContext("2d");
// Unit size of the grid
const box = 20;
// Create the snake
let snake = [];
snake[0] = { x: 9 * box, y: 10 * box };
// Create the food
let food = {
  x: Math.floor(Math.random() * 19 + 1) * box,
  y: Math.floor(Math.random() * 19 + 1) * box
};
// Initial snake direction
let direction;
// Score
let score = 0;
// Speed variables
let speed = 100;
let wallOn = true;
// Control the snake with keyboard
document.addEventListener("keydown", changeDirection);
function changeDirection(event) {
  if (event.keyCode == 37 && direction != "RIGHT") {
    direction = "LEFT";
  } else if (event.keyCode == 38 && direction != "DOWN") {
    direction = "UP";
  } else if (event.keyCode == 39 && direction != "LEFT") {
    direction = "RIGHT";
  } else if (event.keyCode == 40 && direction != "UP") {
    direction = "DOWN";
  }
}
function collision(head, array) {
  for (let i = 0; i < array.length; i++) {
    if (head.x == array[i].x && head.y == array[i].y) {
      return true;
    }
  }
  return false;
}
// Draw everything on the canvas
function draw() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  // Draw snake with emoji
  for (let i = 0; i < snake.length; i++) {
    ctx.font = "20px Arial"; // Set font size to match the grid
    ctx.fillText("🩷", snake[i].x, snake[i].y + box); // Adjust the y-offset slightly for better alignment
  }
  // Draw food
  ctx.fillStyle = "white";
  ctx.fillRect(food.x, food.y, box, box);
  // Old head position
  let snakeX = snake[0].x;
  let snakeY = snake[0].y;
  // Move the snake
  if (direction == "LEFT") snakeX -= box;
  if (direction == "UP") snakeY -= box;
  if (direction == "RIGHT") snakeX += box;
  if (direction == "DOWN") snakeY += box;
  // Snake eats the food
  if (snakeX == food.x && snakeY == food.y) {
    score++;
    food = {
      x: Math.floor(Math.random() * 19 + 1) * box,
      y: Math.floor(Math.random() * 19 + 1) * box
    };
  } else {
    snake.pop();
  }
  // New head
  let newHead = {
    x: snakeX,
    y: snakeY
  };
  // Game over conditions
  if (wallOn) {
    if (snakeX < 0 || snakeY < 0 || snakeX >= canvas.width || snakeY >= canvas.height || collision(newHead, snake)) {
      document.getElementById("game-over").style.display = "block";
      clearInterval(game);
    }
  } else {
    // Wrap the snake around the canvas
    if (snakeX < 0) {
      snakeX = canvas.width - box;
    }
    if (snakeX >= canvas.width) {
      snakeX = 0;
    }
    if (snakeY < 0) {
      snakeY = canvas.height - box;
    }
    if (snakeY >= canvas.height) {
      snakeY = 0;
    }
  }
  snake.unshift(newHead);
  // Score display
  ctx.fillStyle = "black";
  ctx.font = "20px Arial";
  ctx.fillText("Score: " + score, 10, 30);
}
// Control speed of the game
let game = setInterval(draw, speed);
// Button functionality
document.getElementById("slow-btn").addEventListener("click", function() {
  clearInterval(game);
  speed = 200; // Slow mode speed
  game = setInterval(draw, speed);
});
document.getElementById("fast-btn").addEventListener("click", function() {
  clearInterval(game);
  speed = 50; // Fast mode speed
  game = setInterval(draw, speed);
});
document.getElementById("wall-btn").addEventListener("click", function() {
  wallOn = !wallOn; // Toggle wall on/off
});
// Theme switching functionality
const themes = ['light-theme', 'dark-theme', 'blue-theme', 'red-theme', 'green-theme', 'grey-theme'];
let currentTheme = 0;
document.getElementById("theme-btn").addEventListener("click", function() {
  // Remove the current theme class
  document.body.classList.remove(themes[currentTheme]);
  // Move to the next theme
  currentTheme = (currentTheme + 1) % themes.length;
  // Apply the new theme
  document.body.classList.add(themes[currentTheme]);
});
</script>