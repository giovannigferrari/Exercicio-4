<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cálculo de Gasto de Combustível</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        input, button {
            padding: 10px;
            margin: 5px;
        }
        .result {
            margin-top: 20px;
        }
        .container{
            align-items: center;
            align-content: center;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
    <h1>Calculadora de Gasto de Combustível</h1>
    <label for="kmInput">Informe a quilometragem percorrida (em km):</label>
    <input type="number" id="kmInput" placeholder="Digite a quilometragem" />
    <label for="valorCombustivel">Informe o valor do combustível (por litro):</label>
    <input type="number" id="valorCombustivel" placeholder="Digite o valor (R$)" step="0.01" />
    <button onclick="calcularGasto()">Calcular Gasto</button>
    <div class="result">
        <p>Consumo total de combustível: <span id="consumoCombustivel"></span> litros</p>
        <p>Gasto total: R$ <span id="gastoTotal"></span></p>
    </div>
    </div>
    <script>
        function calcularGasto() {
            const kmPercorridos = parseFloat(document.getElementById('kmInput').value);
            const valorCombustivel = parseFloat(document.getElementById('valorCombustivel').value);
            if (isNaN(kmPercorridos) || isNaN(valorCombustivel) || kmPercorridos <= 0 || valorCombustivel <= 0) {
                alert("Por favor, insira valores válidos.");
                return;
            }
            const consumoPorKm = 8;
            const consumoCombustivel = kmPercorridos / consumoPorKm;
            document.getElementById('consumoCombustivel').textContent = consumoCombustivel.toFixed(2);
            const gastoTotal = consumoCombustivel * valorCombustivel;
            document.getElementById('gastoTotal').textContent = gastoTotal.toFixed(2);
        }
    </script>
</body>
</html>
