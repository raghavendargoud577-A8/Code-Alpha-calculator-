# Code-Alpha-calculator-

//Calculator 

// HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" disabled>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="backspace()">DEL</button>
            <button onclick="append('/')">/</button>
            <button onclick="append('*')">*</button>
            <button onclick="append('7')">7</button>
            <button onclick="append('8')">8</button>
            <button onclick="append('9')">9</button>
            <button onclick="append('-')">-</button>
            <button onclick="append('4')">4</button>
            <button onclick="append('5')">5</button>
            <button onclick="append('6')">6</button>
            <button onclick="append('+')">+</button>
            <button onclick="append('1')">1</button>
            <button onclick="append('2')">2</button>
            <button onclick="append('3')">3</button>
            <button onclick="calculate()">=</button>
            <button onclick="append('0')">0</button>
            <button onclick="append('.')">.</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>



// CSS 

.calculator {
    width: 250px;
    margin: 50px auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

#display {
    width: 100%;
    height: 40px;
    font-size: 24px;
    text-align: right;
    padding: 10px;
    border: none;
    border-bottom: 1px solid #ccc;
    margin-bottom: 20px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    height: 40px;
    font-size: 18px;
    border: none;
    border-radius: 10px;
    background-color: #f0f0f0;
    cursor: pointer;
}

button:hover {
    background-color: #ddd;
}


//Javascript 

let displayValue = '';

function append(value) {
    displayValue += value;
    document.getElementById('display').value = displayValue;
}

function clearDisplay() {
    displayValue = '';
    document.getElementById('display').value = displayValue;
}

function backspace() {
    displayValue = displayValue.slice(0, -1);
    document.getElementById('display').value = displayValue;
}

function calculate() {
    try {
        const result = eval(displayValue);
        displayValue = result;
        document.getElementById('display').value = displayValue;
    } catch (error) {
        displayValue = 'Error';
        document.getElementById('display').value = displayValue;
    }
}
