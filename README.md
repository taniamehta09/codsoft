# codsoft
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Calculator</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #f0f4f7;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            width: 320px;
            padding: 20px;
            background-color: #ffffff;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        .calculator {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        input {
            grid-column: span 4;
            height: 50px;
            text-align: right;
            font-size: 1.5em;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f7f7f7;
        }

        button {
            height: 50px;
            font-size: 1.2em;
            color: #333;
            border: none;
            border-radius: 5px;
            background-color: #e0e0e0;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        button:hover {
            background-color: #d4d4d4;
        }

        .equal {
            grid-column: span 2;
            background-color: #4caf50;
            color: white;
        }

        .equal:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
  <div class="container">
    <div class="calculator">
        <input type="text" placeholder="0" id="outputscreen" readonly>
        <button onclick="Clear()">C</button>
        <button onclick="del()">DEL</button>
        <button onclick="display('%')">%</button>
        <button onclick="display('/')">/</button>
        <button onclick="display('7')">7</button>
        <button onclick="display('8')">8</button>
        <button onclick="display('9')">9</button>
        <button onclick="display('*')">*</button>
        <button onclick="display('4')">4</button>
        <button onclick="display('5')">5</button>
        <button onclick="display('6')">6</button>
        <button onclick="display('-')">-</button>
        <button onclick="display('1')">1</button>
        <button onclick="display('2')">2</button>
        <button onclick="display('3')">3</button>
        <button onclick="display('+')">+</button>
        <button onclick="display('.')">.</button>
        <button onclick="display('0')">0</button>
        <button onclick="Calculate()" class="equal">=</button>
    </div>
  </div>
  <script>
      let outputScreen = document.getElementById("outputscreen");

      function display(num) {
          outputScreen.value += num;
      }

      function Calculate() {
          try {
              outputScreen.value = eval(outputScreen.value);
          } catch (err) {
              alert("Invalid");
          }
      }

      function Clear() {
          outputScreen.value = "";
      }

      function del() {
          outputScreen.value = outputScreen.value.slice(0, -1);
      }
  </script>
</body>
</html>
