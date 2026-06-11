    <title>Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: #f0f0f0;
        }

        .calculator {
            width: 300px;
            background: #222;
            padding: 20px;
            border-radius: 10px;
        }

        #display {
            width: 100%;
            height: 60px;
            font-size: 24px;
            text-align: right;
            margin-bottom: 10px;
            padding-right: 10px;
            border: none;
            border-radius: 5px;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        button {
            height: 60px;
            font-size: 22px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            opacity: 0.8;
        }

        .operator {
            background: orange;
            color: white;
        }

        .clear {
            background: red;
            color: white;
        }

        .equal {
            background: green;
            color: white;
        }
    </style>
</head>
<body>

<div class="calculator">
    <input type="text" id="display" readonly>

    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button onclick="appendValue('/')">/</button>
        <button onclick="appendValue('*')">*</button>
        <button onclick="appendValue('-')">-</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button class="operator" onclick="appendValue('+')">+</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button onclick="appendValue('.')">.</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button class="equal" onclick="calculate()">=</button>

        <button style="grid-column: span 4;" onclick="appendValue('0')">0</button>
    </div>
</div>

<script>
    function appendValue(value) {
        document.getElementById("display").value += value;
    }

    function clearDisplay() {
        document.getElementById("display").value = "";
    }

    function calculate() {
        try {
            document.getElementById("display").value =
                eval(document.getElementById("display").value);
        } catch {
            alert("Invalid Expression");
        }
    }
</script>

</body>
</html>
