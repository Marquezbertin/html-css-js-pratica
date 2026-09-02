# Módulo 07 — JavaScript Básico

## O que você vai aprender

JavaScript é a linguagem que torna as páginas web interativas. Neste módulo, você vai aprender variáveis, operadores, condicionais, loops e funções — a base de toda programação.

## Teoria

### Onde colocar o JavaScript

```html
<!-- No final do body (recomendado) -->
<body>
    <h1>Minha Página</h1>
    <script>
        console.log("Olá, mundo!");
    </script>
</body>

<!-- Ou em arquivo externo -->
<body>
    <script src="app.js"></script>
</body>
```

### Variáveis

```javascript
// let - pode mudar de valor
let nome = "Maria";
let idade = 17;
nome = "Maria Santos"; // Pode reatribuir

// const - NÃO pode mudar de valor
const PI = 3.14159;
const NOME_APP = "MeuApp";
// PI = 3; // ERRO! const não pode ser reatribuída

// var - forma antiga (evite usar)
var velho = "não use";
```

### Tipos de Dados

```javascript
let texto = "Olá";          // String
let numero = 42;             // Number
let decimal = 3.14;          // Number
let verdadeiro = true;       // Boolean
let vazio = null;            // Null
let indefinido = undefined;  // Undefined
```

### Operadores

```javascript
// Aritméticos
let soma = 10 + 5;      // 15
let subtracao = 10 - 5;  // 5
let multiplicacao = 10 * 5; // 50
let divisao = 10 / 5;    // 2
let resto = 10 % 3;      // 1

// Comparação
let igual = 5 == "5";    // true (compara valor)
let estrito = 5 === "5"; // false (compara valor E tipo)
let diferente = 5 != 3;  // true
let maior = 10 > 5;      // true

// Lógicos
let e = true && false;   // false (E)
let ou = true || false;  // true (OU)
let nao = !true;         // false (NÃO)
```

### Condicionais

```javascript
let hora = 14;

if (hora < 12) {
    console.log("Bom dia!");
} else if (hora < 18) {
    console.log("Boa tarde!");
} else {
    console.log("Boa noite!");
}

// Ternário (forma curta)
let saudacao = hora < 12 ? "Bom dia" : "Boa tarde";

// Switch
let dia = "segunda";
switch (dia) {
    case "segunda":
        console.log("Começou a semana!");
        break;
    case "sexta":
        console.log("Sextou!");
        break;
    default:
        console.log("Dia normal");
}
```

### Loops

```javascript
// For - quando sabe quantas vezes repetir
for (let i = 0; i < 5; i++) {
    console.log("Repetição " + i);
}

// While - quando a condição define o fim
let contador = 0;
while (contador < 3) {
    console.log("Contador: " + contador);
    contador++;
}

// For...of - para percorrer arrays
let frutas = ["maçã", "banana", "laranja"];
for (let fruta of frutas) {
    console.log(fruta);
}
```

### Funções

```javascript
// Função declaration
function saudar(nome) {
    return "Olá, " + nome + "!";
}

// Função expression
const somar = function(a, b) {
    return a + b;
};

// Arrow function (forma moderna)
const multiplicar = (a, b) => a * b;

// Chamando as funções
console.log(saudar("Maria"));     // "Olá, Maria!"
console.log(somar(10, 5));        // 15
console.log(multiplicar(3, 4));   // 12
```

### Exemplo Completo — Calculadora de IMC

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de IMC</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            padding: 40px;
            background: #f0f0f0;
        }
        .calculadora {
            background: white;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        input {
            padding: 10px;
            margin: 5px 0;
            width: 200px;
            border: 1px solid #ddd;
            border-radius: 6px;
        }
        button {
            padding: 10px 20px;
            background: #0077ff;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            margin-top: 10px;
        }
        #resultado {
            margin-top: 15px;
            padding: 15px;
            border-radius: 8px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="calculadora">
        <h2>Calculadora de IMC</h2>
        <label>Altura (m):</label><br>
        <input type="number" id="altura" step="0.01" placeholder="1.70"><br>
        <label>Peso (kg):</label><br>
        <input type="number" id="peso" placeholder="70"><br>
        <button onclick="calcular()">Calcular</button>
        <div id="resultado"></div>
    </div>

    <script>
        function calcular() {
            let altura = parseFloat(document.getElementById("altura").value);
            let peso = parseFloat(document.getElementById("peso").value);

            if (isNaN(altura) || isNaN(peso) || altura <= 0 || peso <= 0) {
                document.getElementById("resultado").innerHTML = "Preencha corretamente!";
                return;
            }

            let imc = peso / (altura * altura);
            let classificacao = "";

            if (imc < 18.5) {
                classificacao = "Abaixo do peso";
            } else if (imc < 25) {
                classificacao = "Peso normal";
            } else if (imc < 30) {
                classificacao = "Sobrepeso";
            } else {
                classificacao = "Obesidade";
            }

            document.getElementById("resultado").innerHTML =
                "IMC: " + imc.toFixed(1) + " — " + classificacao;
        }
    </script>
</body>
</html>
```

## Exercícios

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Variáveis e operadores | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Condicionais | ⭐ Fácil |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Loops e arrays | ⭐⭐ Médio |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Funções | ⭐⭐ Médio |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Mini-projeto calculadora | ⭐⭐⭐ Difícil |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Jogo de adivinhação | ⭐⭐⭐ Difícil |
