<!DOCTYPE html>
<html>
<head>
<title>Upgrade - Level Game</title>
<style>
body{
  font-family: Arial;
  background:#111;
  color:white;
  text-align:center;
  margin:0;
  padding:0;
}
header{
  background:#cc0000; /* red menu */
  padding:20px;
}
button{
  padding:10px 20px;
  margin:5px;
  cursor:pointer;
  background:#ff4444;
  color:white;
  border:none;
  border-radius:5px;
  font-size:16px;
}
button:hover{ background:#ff0000; }
canvas{
  background:#333;
  display:block;
  margin:20px auto;
  border:2px solid #fff;
}
</style>
</head>
<body>

<header id="menu">
  <h1>🎮 Upgrade: Level Game</h1>
  <p>Pick a level to start</p>
  <button onclick="startLevel(1)">Level 1</button>
  <button onclick="startLevel(2)">Level 2</button>
  <button onclick="startLevel(3)">Level 3</button>
</header>

<canvas id="gameCanvas" width="600" height="400" style="display:none;"></canvas>
<p id="scoreDisplay"></p>

<script>
// Game variables
const canvas = document.getElementById("gameCanvas");
const ctx = canvas.getContext("2d");

let player = {x:50, y:350, width:30, height:30, vy:0};
let gravity = 0.5;
let obstacles = [];
let score = 0;
let level = 
