# JavaScript Calculator README

## Overview

This is a simple and responsive calculator application built with plain JavaScript, HTML, and CSS. The calculator provides basic arithmetic operations like addition, subtraction, multiplication, and division. It is designed to demonstrate the use of JavaScript for building interactive web applications without any frameworks or libraries.

## Features

- **Basic Arithmetic Operations:** Perform addition, subtraction, multiplication, and division.
- **Clear Function:** Reset the calculator display and clear all operations.
- **Responsive Design:** Adjusts to different screen sizes for mobile and desktop use.
- **User-friendly Interface:** Simple and intuitive layout for ease of use.

## Technologies Used

- **Front-end:** HTML, CSS, JavaScript

## Getting Started

### Prerequisites

No special prerequisites are needed other than a web browser.

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/javascript-calculator.git
   cd javascript-calculator
   ```

2. **Open the application:**
   - Simply open the `index.html` file in your web browser.

### Running the Application

1. **Open the `index.html` file:**
   - Navigate to the project directory and open the `index.html` file in your web browser.

### Project Structure

- `index.html`: Main HTML file containing the structure of the calculator.
- `style.css`: CSS file for styling the calculator.
- `script.js`: JavaScript file containing the logic of the calculator.

## Usage

1. **Launching the Calculator:**
   - Open the `index.html` file in your web browser.

2. **Performing Calculations:**
   - Click on the number buttons to input values.
   - Use the operation buttons (+, -, *, /) to perform calculations.
   - Press the "=" button to get the result.
   - Use the "C" button to clear the display and reset the calculator.

## Code Overview

### HTML (`index.html`)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="calculator">
        <div class="display" id="display">0</div>
        <div class="buttons">
            <button class="btn" onclick="clearDisplay()">C</button>
            <button class="btn" onclick="appendNumber('7')">7</button>
            <button class="btn" onclick="appendNumber('8')">8</button>
            <button class="btn" onclick="appendNumber('9')">9</button>
            <button class="btn" onclick="chooseOperation('/')">/</button>
            <button class="btn" onclick="appendNumber('4')">4</button>
            <button class="btn" onclick="appendNumber('5')">5</button>
            <button class="btn" onclick="appendNumber('6')">6</button>
            <button class="btn" onclick="chooseOperation('*')">*</button>
            <button class="btn" onclick="appendNumber('1')">1</button>
            <button class="btn" onclick="appendNumber('2')">2</button>
            <button class="btn" onclick="appendNumber('3')">3</button>
            <button class="btn" onclick="chooseOperation('-')">-</button>
            <button class="btn" onclick="appendNumber('0')">0</button>
            <button class="btn" onclick="appendDot()">.</button>
            <button class="btn" onclick="calculate()">=</button>
            <button class="btn" onclick="chooseOperation('+')">+</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

### CSS (`style.css`)

```css
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f4f4f9;
    margin: 0;
    font-family: Arial, sans-serif;
}

.calculator {
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
    width: 300px;
}

.display {
    background-color: #222;
    color: #fff;
    font-size: 2rem;
    padding: 20px;
    text-align: right;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    overflow: hidden;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
}

.btn {
    background-color: #f0f0f0;
    border: 1px solid #ddd;
    padding: 20px;
    font-size: 1.5rem;
    cursor: pointer;
}

.btn:hover {
    background-color: #ddd;
}
```

### JavaScript (`script.js`)

```javascript
let displayValue = '0';
let firstOperand = null;
let secondOperand = null;
let currentOperation = null;

function updateDisplay() {
    const display = document.getElementById('display');
    display.innerText = displayValue;
}

function clearDisplay() {
    displayValue = '0';
    firstOperand = null;
    secondOperand = null;
    currentOperation = null;
    updateDisplay();
}

function appendNumber(number) {
    if (displayValue === '0') {
        displayValue = number;
    } else {
        displayValue += number;
    }
    updateDisplay();
}

function appendDot() {
    if (!displayValue.includes('.')) {
        displayValue += '.';
    }
    updateDisplay();
}

function chooseOperation(operation) {
    if (currentOperation !== null) {
        calculate();
    }
    firstOperand = parseFloat(displayValue);
    currentOperation = operation;
    displayValue = '0';
}

function calculate() {
    if (currentOperation === null || firstOperand === null) {
        return;
    }
    secondOperand = parseFloat(displayValue);
    let result;
    switch (currentOperation) {
        case '+':
            result = firstOperand + secondOperand;
            break;
        case '-':
            result = firstOperand - secondOperand;
            break;
        case '*':
            result = firstOperand * secondOperand;
            break;
        case '/':
            result = firstOperand / secondOperand;
            break;
        default:
            return;
    }
    displayValue = result.toString();
    currentOperation = null;
    firstOperand = null;
    secondOperand = null;
    updateDisplay();
}
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/your-feature-name`
3. Make your changes and commit them: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Contact

If you have any questions, feel free to reach out:

- Email: anishakodavati7@gmail.com
- GitHub: https://github.com/KodavatiAnisha/writingcalculator

---

This README provides an overview and instructions to help you get started with developing and contributing to the JavaScript Calculator project. Adjust the details as needed for your specific project requirements.
