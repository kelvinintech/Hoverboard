# Hoverboard

This project is a simple hoverboard effect created using JavaScript, HTML, and CSS. The hoverboard consists of a grid of squares that change color when hovered over, creating a visually appealing interactive experience.

## Table of Contents

- [Overview](#overview)
- [Code Explanation](#code-explanation)
- [What I Learned](#what-i-learned)
- [Usage](#usage)
- [License](#license)

## Overview

The hoverboard effect is achieved by dynamically creating a grid of squares and applying color changes and shadow effects when the squares are hovered over. This project demonstrates basic DOM manipulation, event handling, and the use of random colors to create an engaging user interface.

## Code Explanation

```javascript
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



## Breakdown
Selecting the Container: The container element is selected using document.getElementById.

Color Array: An array of colors is defined. These colors will be used to set the background and box shadow of the squares.

Creating Squares: A loop runs 500 times (as defined by SQUARES), creating a div element for each iteration. These div elements are given the class square.

Event Listeners: Two event listeners are added to each square:

mouseover: Triggers the setColor function to change the square's color.
mouseout: Triggers the removeColor function to revert the square's color.
Appending Squares: Each square is appended to the container.

Setting Color: The setColor function changes the background and box shadow of a square to a random color from the array.

Removing Color: The removeColor function resets the square's background and box shadow to the default values.

Getting Random Color: The getRandomColor function returns a random color from the colors array.

What I Learned
Working on this hoverboard project taught me several important concepts and skills:

DOM Manipulation: I gained a deeper understanding of how to create and manipulate DOM elements dynamically using JavaScript.

Event Handling: I learned how to add and manage event listeners to create interactive web elements.

CSS Styling: The project reinforced my knowledge of applying styles dynamically using JavaScript, including how to use box shadows to create visual effects.

Randomization: I learned how to implement randomization in JavaScript to enhance the interactivity of web elements.

Debugging: Through trial and error, I improved my debugging skills, learning how to identify and fix issues in both JavaScript and CSS.

Overall, this project was a great opportunity to apply and enhance my front-end development skills.

Usage
To use this hoverboard effect in your own project, simply include the JavaScript code in a script tag and ensure you have a container element in your HTML with the id container. You can customize the number of squares and colors by modifying the SQUARES constant and colors array, respectively.

License
This project is open-source and available under the MIT License.

Created by @Kelvinintech
