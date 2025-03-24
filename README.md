# Calculator-ShinsOcT

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modern Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #121212;
            font-family: Arial, sans-serif;
        }
        .calculator {
            background: #1e1e1e;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.1);
            text-align: center;
        }
        .display {
            width: 100%;
            height: 60px;
            text-align: right;
            font-size: 2em;
            margin-bottom: 15px;
            padding: 10px;
            border: none;
            border-radius: 10px;
            background-color: #333;
            color: white;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 12px;
        }
        button {
            padding: 20px;
            font-size: 1.5em;
            cursor: pointer;
            border: none;
            border-radius: 10px;
            background-color: #292929;
            color: white;
            transition: 0.3s;
        }
        button:hover {
            background-color: #3a3a3a;
        }
        .clear {
            background-color: #e74c3c;
        }
        .clear:hover {
            background-color: #c0392b;
        }
        .operator {
            background-color: #f39c12;
        }
        .operator:hover {
            background-color: #e67e22;
        }
        .equal {
            background-color: #27ae60;
        }
        .equal:hover {
            background-color: #219150;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" class="display" disabled>
        <div class="buttons">
            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('/')" class="operator">÷</button>
            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="appendValue('×')" class="operator">×</button>
            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button onclick="appendValue('-')" class="operator">-</button>
            <button onclick="appendValue('0')">0</button>
            <button onclick="clearDisplay()" class="clear">C</button>
            <button onclick="calculateResult()" class="equal">=</button>
            <button onclick="appendValue('+')" class="operator">+</button>
        </div>
    </div>
    <script>
        function appendValue(value) {
            document.getElementById('display').value += value;
        }
        function clearDisplay() {
            document.getElementById('display').value = '';
        }
        function calculateResult() {
            try {
                let expression = document.getElementById('display').value.replace(/×/g, '*').replace(/÷/g, '/');
                document.getElementById('display').value = eval(expression);
            } catch {
                document.getElementById('display').value = 'Error';
            }
        }
    </script>
</body>
</html> 
