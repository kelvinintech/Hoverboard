# Hoverboard

This project is a simple hoverboard effect created using JavaScript, HTML, and CSS. The hoverboard consists of a grid of squares that change color when hovered over, creating a visually appealing interactive experience.


## Overview

The hoverboard effect is achieved by dynamically creating a grid of squares and applying color changes and shadow effects when the squares are hovered over. This project demonstrates basic DOM manipulation, event handling, and the use of random colors to create an engaging user interface.

## Code Explanation

```javascript 🤷🏽‍♂️
const container = document.getElementById("container");

const colors = ["#e74c3c", "#8e44ad", "#3499db", "#e67e22", "#2ecc71"];

const SQUARES = 500;

for (let i = 0; i < SQUARES; i++) {
  const square = document.createElement("div");
  square.classList.add("square");

  square.addEventListener("mouseover", () => setColor(square));
  square.addEventListener("mouseout", () => removeColor(square));

  container.appendChild(square);
}

function setColor(element) {
  const color = getRandomColor();
  element.style.background = color;
  element.style.boxShadow = `0 0 2px ${color}, 0 0 10px ${color}`;
}

function removeColor(element) {
  element.style.background = "#1d1d1d";
  element.style.boxShadow = "0 0 2px #000";
}

function getRandomColor() {
  return colors[Math.floor(Math.random() * colors.length)];
}
