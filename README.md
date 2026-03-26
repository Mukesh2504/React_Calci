# Ex04 Simple Calculator - React Project
## Date:12.03.26

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
HTML
```
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Advanced Calculator</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="calculator">
      <input type="text" id="display" disabled />

      <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button onclick="deleteLast()">⌫</button>
        <button onclick="appendValue('%')">%</button>
        <button onclick="appendValue('/')">÷</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button onclick="appendValue('*')">×</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button onclick="appendValue('-')">−</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button onclick="appendValue('+')">+</button>

        <button onclick="appendValue('.')">.</button>
        <button onclick="appendValue('0')">0</button>
        <button class="equal" onclick="calculate()">=</button>
      </div>
    </div>

    <script src="script.js"></script>
  </body>
</html>
```
Script.js
```
let display = document.getElementById("display");

// Add value
function appendValue(value) {
    display.value += value;
}

// Clear display
function clearDisplay() {
    display.value = "";
}

// Delete last character
function deleteLast() {
    display.value = display.value.slice(0, -1);
}

// Calculate result safely
function calculate() {
    try {
        display.value = eval(display.value);
    } catch (error) {
        display.value = "Error";
    }
}

// Keyboard support
document.addEventListener("keydown", function (event) {
    if (
        (event.key >= "0" && event.key <= "9") ||
        ["+", "-", "*", "/", ".", "%"].includes(event.key)
    ) {
        appendValue(event.key);
    }

    if (event.key === "Enter") {
        calculate();
    }

    if (event.key === "Backspace") {
        deleteLast();
    }

    if (event.key === "Escape") {
        clearDisplay();
    }
});
```

css
```
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Segoe UI', sans-serif;
}

/* Glassmorphism container */
.calculator {
  width: 320px;
  padding: 25px;
  border-radius: 20px;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(15px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
}

/* Display */
#display {
  width: 100%;
  height: 70px;
  font-size: 28px;
  text-align: right;
  padding: 15px;
  border-radius: 12px;
  border: none;
  outline: none;
  background: rgba(0, 0, 0, 0.7);
  color: #fff;
  margin-bottom: 20px;
}

/* Buttons grid */
.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
}

/* Base button style */
button {
  height: 60px;
  font-size: 18px;
  border: none;
  border-radius: 14px;
  cursor: pointer;
  transition: transform 0.15s ease, box-shadow 0.15s ease, background 0.2s;
}

/* Number buttons */
button {
  background: rgba(255, 255, 255, 0.15);
  color: #fff;
}

/* Operator buttons */
button:nth-child(4n),
button:nth-child(1),
button:nth-child(2),
button:nth-child(3) {
  background: rgba(255, 165, 0, 0.85);
  color: #000;
  font-weight: bold;
}

/* Clear button */
.clear {
  background: rgba(255, 99, 71, 0.9);
  color: white;
}

/* Equal button */
.equal {
  grid-column: span 2;
  background: linear-gradient(135deg, #00f260, #0575e6);
  color: white;
  font-weight: bold;
}

/* Hover effect */
button:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.4);
}

/* Click effect */
button:active {
  transform: scale(0.96);
}
```

## OUTPUT
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/cfd274fc-a193-491e-a068-abd89ac8fb4a" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
