# Calculator

## PROGRAM
```C
index.html

<!DOCTYPE html>
<html>
<head>
  <title>Calculator</title>
  <style>
    body {
      font-family: sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      background-image: url('background.jpg'); /* Add this line */
      background-size: cover;
      background-color: #de7473;
    }

   .calculator {    
      background-color: #c29bd6;
      padding: 20px;
      border-radius: 5px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    }

   .display {
      background-color: #ebffb0;
      padding: 10px;
      text-align: right;
      font-size: 20px;
      border-radius: 5px;
      margin-bottom: 10px;
    }

   .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      grid-gap: 10px;
    }

    button {
      padding: 10px;
      border: none;
      border-radius: 5px;
      background-color: #ccc;
      cursor: pointer;
      font-size: 18px;
    }

    button:hover {
      background-color: #bbb;
    }
  </style>
</head>
<body>

  <div class="calculator">
    <div class="display" id="display"></div>
    <div class="buttons">
      <button onclick="appendNumber('7')">7</button>
      <button onclick="appendNumber('8')">8</button>
      <button onclick="appendNumber('9')">9</button>
      <button onclick="appendOperator('/')">/</button>
      <button onclick="appendNumber('4')">4</button>
      <button onclick="appendNumber('5')">5</button>
      <button onclick="appendNumber('6')">6</button>
      <button onclick="appendOperator('*')">*</button>
      <button onclick="appendNumber('1')">1</button>
      <button onclick="appendNumber('2')">2</button>
      <button onclick="appendNumber('3')">3</button>
      <button onclick="appendOperator('-')">-</button>
      <button onclick="appendNumber('0')">0</button>
      <button onclick="appendNumber('.')">.</button>
      <button onclick="calculate()">=</button>
      <button onclick="appendOperator('+')">+</button>
      <button onclick="clearDisplay()">C</button>
    </div>
  </div>

  <script>
    let display = document.getElementById('display');
    let currentInput = '';
    let operator = null;
    let previousOperand = null;

    function appendNumber(number) {
      currentInput += number;
      display.textContent = currentInput;
    }

    function appendOperator(op) {
      if (operator) {
        calculate();
      }
      previousOperand = parseFloat(currentInput);
      currentInput = '';
      operator = op;
    }

    function calculate() {
      let currentOperand = parseFloat(currentInput);
      if (operator === '+') {
        currentInput = (previousOperand + currentOperand).toString();
      } else if (operator === '-') {
        currentInput = (previousOperand - currentOperand).toString();
      } else if (operator === '*') {
        currentInput = (previousOperand * currentOperand).toString();
      } else if (operator === '/') {
        currentInput = (previousOperand / currentOperand).toString();
      }
      operator = null;
      previousOperand = null;
      display.textContent = currentInput;
    }

    function clearDisplay() {
      currentInput = '';
      operator = null;
      previousOperand = null;
      display.textContent = '';
    }
  </script>

</body>
</html>

```

## OUTPUT
![Screenshot (24)](https://github.com/user-attachments/assets/9ba79291-251e-4a50-a77f-ed9e9ca3d109)
![Screenshot (25)](https://github.com/user-attachments/assets/ec691307-45e1-41f1-a8ab-7a849002ab48)


