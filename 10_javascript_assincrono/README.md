# Módulo 10 — JavaScript Assíncrono

## O que você vai aprender

Nem tudo acontece instantaneamente na web. Carregar dados, esperar respostas de servidores e lidar com operações que demoram são tarefas fundamentais. Neste módulo, você vai aprender setTimeout, fetch, async/await e como consumir APIs.

## Teoria

### setTimeout e setInterval

```javascript
// Executa DEPOIS de um tempo (uma vez)
setTimeout(function() {
    console.log("Executou depois de 2 segundos!");
}, 2000);

// Arrow function
setTimeout(() => {
    console.log("Isso também!");
}, 1000);

// Intervalo (repete a cada tempo)
let contador = 0;
let intervalo = setInterval(function() {
    contador++;
    console.log("Contador: " + contador);
    if (contador >= 5) {
        clearInterval(intervalo); // Para o intervalo
    }
}, 1000);
```

### Promises

```javascript
// Criando uma Promise
function buscarDados() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            let dados = { nome: "Maria", idade: 17 };
            resolve(dados);
            // reject(new Error("Erro ao buscar dados"));
        }, 2000);
    });
}

// Usando a Promise
buscarDados()
    .then(dados => console.log(dados))
    .catch(erro => console.error(erro))
    .finally(() => console.log("Finalizado"));
```

### Fetch API

```javascript
// GET simples
fetch("https://jsonplaceholder.typicode.com/users")
    .then(response => response.json())
    .then(dados => console.log(dados))
    .catch(erro => console.error(erro));

// POST com dados
fetch("https://jsonplaceholder.typicode.com/posts", {
    method: "POST",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringify({
        title: "Novo Post",
        body: "Conteúdo do post",
        userId: 1
    })
})
.then(response => response.json())
.then(dados => console.log(dados));
```

### Async/Await (forma moderna)

```javascript
// Função assíncrona
async function carregarDados() {
    try {
        let response = await fetch("https://jsonplaceholder.typicode.com/users");
        let dados = await response.json();
        console.log(dados);
        return dados;
    } catch (erro) {
        console.error("Erro:", erro);
    }
}

// Chamando
carregarDados();
```

### APIs Úteis para Praticar

```javascript
// Posts - https://jsonplaceholder.typicode.com/posts
// Usuários - https://jsonplaceholder.typicode.com/users
// Fotos - https://jsonplaceholder.typicode.com/photos
// Tarefas - https://jsonplaceholder.typicode.com/todos
// Pokémons - https://pokeapi.co/api/v2/pokemon/pikachu
// Piadas - https://official-joke-api.appspot.com/random_joke
```

### Exemplo Completo — Buscador de Pokémons

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pokédex</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body {
            font-family: Arial, sans-serif;
            background: #f5f5f5;
            padding: 20px;
        }
        .buscador {
            text-align: center;
            margin-bottom: 30px;
        }
        .buscador input {
            padding: 12px 20px;
            width: 300px;
            border: 2px solid #ddd;
            border-radius: 25px;
            font-size: 16px;
        }
        .buscador button {
            padding: 12px 25px;
            background: #ff6b6b;
            color: white;
            border: none;
            border-radius: 25px;
            font-size: 16px;
            cursor: pointer;
            margin-left: 10px;
        }
        .pokemon-card {
            background: white;
            max-width: 350px;
            margin: 0 auto;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            display: none;
        }
        .pokemon-card img {
            width: 150px;
            height: 150px;
        }
        .pokemon-card h2 {
            color: #333;
            margin: 10px 0;
            text-transform: capitalize;
        }
        .stat {
            display: flex;
            justify-content: space-between;
            padding: 5px 0;
            border-bottom: 1px solid #eee;
        }
        #erro {
            text-align: center;
            color: red;
            margin-top: 20px;
        }
        #loading {
            text-align: center;
            margin-top: 20px;
            display: none;
        }
    </style>
</head>
<body>
    <div class="buscador">
        <input type="text" id="busca" placeholder="Nome do Pokémon...">
        <button onclick="buscarPokemon()">Buscar</button>
    </div>
    <div id="loading">Carregando...</div>
    <div id="erro"></div>
    <div class="pokemon-card" id="card">
        <img id="foto" src="" alt="">
        <h2 id="nome"></h2>
        <div id="stats"></div>
    </div>

    <script>
        async function buscarPokemon() {
            let nome = document.getElementById("busca").value.toLowerCase().trim();
            if (!nome) return;

            document.getElementById("loading").style.display = "block";
            document.getElementById("card").style.display = "none";
            document.getElementById("erro").innerText = "";

            try {
                let response = await fetch(
                    "https://pokeapi.co/api/v2/pokemon/" + nome
                );
                if (!response.ok) throw new Error("Pokémon não encontrado");

                let dados = await response.json();

                document.getElementById("foto").src = dados.sprites.front_default;
                document.getElementById("nome").innerText = dados.name;

                let statsHTML = "";
                dados.stats.forEach(stat => {
                    statsHTML += '<div class="stat">' +
                        '<span>' + stat.stat.name + '</span>' +
                        '<span>' + stat.base_stat + '</span>' +
                        '</div>';
                });
                document.getElementById("stats").innerHTML = statsHTML;
                document.getElementById("card").style.display = "block";

            } catch (erro) {
                document.getElementById("erro").innerText = erro.message;
            } finally {
                document.getElementById("loading").style.display = "none";
            }
        }

        // Buscar com Enter
        document.getElementById("busca").addEventListener("keypress", function(e) {
            if (e.key === "Enter") buscarPokemon();
        });
    </script>
</body>
</html>
```

## Exercícios

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | setTimeout e setInterval | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Promises e fetch básico | ⭐⭐ Médio |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Consumir API de usuários | ⭐⭐ Médio |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Pokédex completa | ⭐⭐⭐ Difícil |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Previsão do tempo | ⭐⭐⭐ Difícil |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Dashboard com múltiplas APIs | ⭐⭐⭐⭐ Expert |
