---
layout: page
title: Calculator
description: To solve stuff
permalink: /calculator/

---

{% include nav/home.html %}

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
            margin: 0;
        }

        .calculator {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        .calculator input {
            width: 100%;
            height: 40px;
            text-align: right;
            margin-bottom: 10px;
            font-size: 18px;
            padding: 5px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 10px;
        }

        .buttons button {
            width: 100%;
            padding: 15px;
            background-color: #f1c40f;
            border: none;
            font-size: 18px;
            cursor: pointer;
            border-radius: 4px;
        }

        .buttons button:hover {
            background-color: #e67e22;
        }

        .buttons button.clear {
            background-color: #e74c3c;
            grid-column: span 2;
        }

        .buttons button.equals {
            background-color: #2ecc71;
            grid-column: span 2;
        }
    </style>
</head>
<body>

    <div class="calculator">
        <input type="text" id="display" disabled>
        <div class="buttons">
            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('/')">/</button>
            
            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="appendValue('*')">*</button>
            
            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button onclick="appendValue('-')">-</button>
            
            <button onclick="appendValue('0')">0</button>
            <button onclick="appendValue('.')">.</button>
            <button class="clear" onclick="clearDisplay()">C</button>
            <button onclick="appendValue('+')">+</button>

            <button class="equals" onclick="calculate()">=</button>
        </div>
    </div>

    <script>
        function appendValue(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculate() {
            let expression = document.getElementById('display').value;
            try {
                document.getElementById('display').value = eval(expression);
            } catch (error) {
                document.getElementById('display').value = 'Error';
            }
        }
    </script>

</body>
</html>
