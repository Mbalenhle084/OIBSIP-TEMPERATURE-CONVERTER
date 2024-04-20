# OIBSIP-TEMPERATURE-CONVERTER
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Temperature Converter</title>

<link rel="stylesheet" href="styles/temperatureConverter.css">
<style>.section{
    background-color: antiquewhite;
    color: pink;
  }
    body {
        font-family: Arial, sans-serif;
    }
    .container {
        width: 300px;
        margin: 50px auto;
    }
    input[type="number"] {
        width: 100%;
        padding: 8px;
        margin: 5px 0;
        box-sizing: border-box;
    }
    button {
        width: 100%;
        padding: 10px;
        margin: 10px 0;
        background-color: #4ca5af;
        color: white;
        border: none;
        cursor: pointer;
    }
    button:hover {
        background-color: #9845a0;
    }
    #output {
        width: 100%;
        padding: 8px;
        margin-top: 10px;
        box-sizing: border-box;
    }
    .error {
        color: red;
    }
</style>
</head>
<body>
  <section class="section">
<div class="container">
    <h2>Temperature Converter</h2>
    <input type="number" id="inputTemp" placeholder="Enter temperature">
    <input type="text" id="output" placeholder="Converted temperature" readonly>
    <p id="errorMessage" class="error" style="display: none;">Please enter a temperature.</p>
    <button onclick="convertToFahrenheit()">Convert to Fahrenheit</button>
    <button onclick="convertToCelsius()">Convert to Celsius</button>
   
</div>
  </section>

<script>
    function convertToFahrenheit() {
        var inputTemp = document.getElementById("inputTemp").value.trim();
        if (inputTemp === "") {
            document.getElementById("errorMessage").style.display = "block";
            return;
        }
        var celsiusTemp = parseFloat(inputTemp);
        var fahrenheitTemp = (celsiusTemp * 9/5) + 32;
        document.getElementById("output").value = fahrenheitTemp.toFixed(2) + "°F";
        document.getElementById("errorMessage").style.display = "none";
    }

    function convertToCelsius() {
        var inputTemp = document.getElementById("inputTemp").value.trim();
        if (inputTemp === "") {
            document.getElementById("errorMessage").style.display = "block";
            return;
        }
        var fahrenheitTemp = parseFloat(inputTemp);
        var celsiusTemp = (fahrenheitTemp - 32) * 5/9;
        document.getElementById("output").value = celsiusTemp.toFixed(2) + "°C";
        document.getElementById("errorMessage").style.display = "none";
    }
</script>
</body>
</html>
