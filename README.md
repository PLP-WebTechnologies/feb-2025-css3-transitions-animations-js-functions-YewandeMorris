# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

<!DOCTYPE html>

<html lang=”en”>

<head>

  <meta charset=”UTF-8”>

  <title>CSS Transition Example</title>

  <style>

    .my-button {

      Padding: 10px 20px;

      Background-color: #3498db;

      Color: white;

      Border: none;

      Border-radius: 5px;

      Font-size: 16px;

      Cursor: pointer;

      Transition: background-color 0.3s ease, transform 0.3s ease;

    }



    .my-button:hover {

      Background-color: #2980b9;

      Transform: scale(1.1);

    }

  </style>

</head>

<body>



  <button class=”my-button”>Hover Me</button>



</body>

</html>



<!DOCTYPE html>

<html lang="en">

<head>

  <meta charset="UTF-8" />

  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>

  <title>Preferences and Animation</title>

  <link rel="stylesheet" href="styles.css" />

</head>

<body>



  <h2>User Preferences & Animation</h2>



  <label>

    Select Theme:

    <select id="themeSelect">

      <option value="light">Light</option>

      <option value="dark">Dark</option>

    </select>

  </label>



  <button id="animateBtn">Animate Box</button>



  <div id="box"></div>



  <script src="script.js"></script>

</body>

</html>



body.light {

  background-color: #ffffff;

  color: #000000;

}



body.dark {

  background-color: #121212;

  color: #ffffff;

}



#box {

  width: 100px;

  height: 100px;

  background-color: #3498db;

  margin-top: 20px;

  transition: transform 0.5s ease;

}



.animate {

  transform: rotate(360deg) scale(1.2);

}



// Function to save user theme

function savePreference(theme) {

  localStorage.setItem('userTheme', theme);

}



// Function to load and apply saved theme

function loadPreference() {

  const savedTheme = localStorage.getItem('userTheme');

  if (savedTheme) {

    document.body.className = savedTheme;

    document.getElementById('themeSelect').value = savedTheme;

  }

}



// Handle theme change

document.getElementById('themeSelect').addEventListener('change', function () {

  const selectedTheme = this.value;

  document.body.className = selectedTheme;

  savePreference(selectedTheme);

});



// Trigger animation

document.getElementById('animateBtn').addEventListener('click', function () {

  const box = document.getElementById('box');

  box.classList.remove('animate'); // Reset animation

  void box.offsetWidth; // Reflow to restart animation

  box.classList.add('animate');

});



// Initialize

loadPreference();











