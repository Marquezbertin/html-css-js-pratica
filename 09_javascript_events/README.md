# Módulo 09 — JavaScript Events (Eventos)

## O que você vai aprender

Eventos são ações que acontecem na página (cliques, digitação, scroll, etc). Neste módulo, você vai aprender a capturar e responder a diferentes tipos de eventos de forma profissional.

## Teoria

### addEventListener (forma recomendada)

```javascript
// Evento de clique
let botao = document.getElementById("meuBotao");
botao.addEventListener("click", function() {
    console.log("Botão clicado!");
});

// Com função nomeada
function handleClick() {
    console.log("Clicado!");
}
botao.addEventListener("click", handleClick);
```

### Tipos de Eventos Comuns

```javascript
// Clique
elemento.addEventListener("click", (e) => { });

// Duplo clique
elemento.addEventListener("dblclick", (e) => { });

// Mouse sobre / sai
elemento.addEventListener("mouseenter", (e) => { });
elemento.addEventListener("mouseleave", (e) => { });

// Teclado
document.addEventListener("keydown", (e) => {
    console.log("Tecla pressionada: " + e.key);
});
document.addEventListener("keyup", (e) => { });

// Submit de formulário
form.addEventListener("submit", (e) => {
    e.preventDefault(); // Impede envio padrão
    // Lógica personalizada
});

// Input / mudança
input.addEventListener("input", (e) => {
    console.log("Valor atual: " + e.target.value);
});
input.addEventListener("change", (e) => { });

// Scroll
window.addEventListener("scroll", (e) => {
    console.log("Rolando... Y: " + window.scrollY);
});

// Resize
window.addEventListener("resize", (e) => {
    console.log("Largura: " + window.innerWidth);
});

// Drag
elemento.addEventListener("dragstart", (e) => { });
elemento.addEventListener("dragover", (e) => { });
elemento.addEventListener("drop", (e) => { });
```

### O Objeto Event

```javascript
elemento.addEventListener("click", function(event) {
    console.log(event.target);     // Elemento que disparou o evento
    console.log(event.type);       // Tipo do evento
    console.log(event.clientX);    // Posição X do mouse
    console.log(event.clientY);    // Posição Y do mouse
    console.log(event.key);        // Tecla pressionada
});
```

### Event Delegation (Delegação de Eventos)

```javascript
// Em vez de adicionar listener em CADA item...
document.querySelectorAll(".item").forEach(item => {
    item.addEventListener("click", handleClick);
});

// ...adicione UM listener no pai
document.getElementById("lista").addEventListener("click", function(e) {
    if (e.target.classList.contains("botao-remover")) {
        e.target.parentElement.remove();
    }
});
```

### Exemplo Completo — Quiz Interativo

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body {
            font-family: Arial, sans-serif;
            background: #f0f0f0;
            display: flex;
            justify-content: center;
            padding: 40px 20px;
        }
        .quiz {
            background: white;
            padding: 30px;
            border-radius: 12px;
            max-width: 600px;
            width: 100%;
        }
        .pergunta {
            font-size: 20px;
            margin-bottom: 20px;
            color: #333;
        }
        .opcao {
            display: block;
            width: 100%;
            padding: 12px;
            margin: 8px 0;
            border: 2px solid #ddd;
            border-radius: 8px;
            background: white;
            cursor: pointer;
            text-align: left;
            font-size: 16px;
            transition: all 0.2s;
        }
        .opcao:hover {
            border-color: #0077ff;
            background: #f0f8ff;
        }
        .opcao.certa {
            border-color: #4caf50;
            background: #e8f5e9;
            color: #2e7d32;
        }
        .opcao.errada {
            border-color: #f44336;
            background: #ffebee;
            color: #c62828;
        }
        #resultado {
            margin-top: 20px;
            padding: 15px;
            border-radius: 8px;
            font-weight: bold;
            text-align: center;
            display: none;
        }
        .proxima {
            margin-top: 15px;
            padding: 10px 20px;
            background: #0077ff;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            display: none;
        }
    </style>
</head>
<body>
    <div class="quiz">
        <div class="pergunta" id="pergunta"></div>
        <div id="opcoes"></div>
        <div id="resultado"></div>
        <button class="proxima" id="proximaBtn">Próxima Pergunta</button>
    </div>

    <script>
        const perguntas = [
            {
                pergunta: "Qual linguagem estiliza páginas web?",
                opcoes: ["HTML", "CSS", "JavaScript", "Python"],
                correta: 1
            },
            {
                pergunta: "Qual tag cria um parágrafo?",
                opcoes: ["<div>", "<span>", "<p>", "<h1>"],
                correta: 2
            },
            {
                pergunta: "Qual propriedade CSS muda a cor de fundo?",
                opcoes: ["color", "font-size", "background-color", "margin"],
                correta: 2
            }
        ];

        let atual = 0;
        let acertos = 0;

        function carregarPergunta() {
            document.getElementById("pergunta").innerText = perguntas[atual].pergunta;
            let html = "";
            perguntas[atual].opcoes.forEach((opcao, i) => {
                html += '<button class="opcao" data-index="' + i + '">' + opcao + '</button>';
            });
            document.getElementById("opcoes").innerHTML = html;
            document.getElementById("resultado").style.display = "none";
            document.getElementById("proximaBtn").style.display = "none";
        }

        document.getElementById("opcoes").addEventListener("click", function(e) {
            if (!e.target.classList.contains("opcao")) return;
            let index = parseInt(e.target.dataset.index);
            let botoes = document.querySelectorAll(".opcao");

            botoes.forEach(btn => {
                btn.disabled = true;
                let i = parseInt(btn.dataset.index);
                if (i === perguntas[atual].correta) {
                    btn.classList.add("certa");
                } else if (i === index) {
                    btn.classList.add("errada");
                }
            });

            if (index === perguntas[atual].correta) {
                acertos++;
                document.getElementById("resultado").innerText = "✅ Correto!";
                document.getElementById("resultado").style.background = "#e8f5e9";
            } else {
                document.getElementById("resultado").innerText = "❌ Errado!";
                document.getElementById("resultado").style.background = "#ffebee";
            }
            document.getElementById("resultado").style.display = "block";
            document.getElementById("proximaBtn").style.display = "block";
        });

        document.getElementById("proximaBtn").addEventListener("click", function() {
            atual++;
            if (atual < perguntas.length) {
                carregarPergunta();
            } else {
                document.getElementById("pergunta").innerText = "Quiz Finalizado!";
                document.getElementById("opcoes").innerHTML =
                    '<p style="text-align:center;font-size:24px;">Acertos: ' + acertos + '/' + perguntas.length + '</p>';
                document.getElementById("proximaBtn").style.display = "none";
            }
        });

        carregarPergunta();
    </script>
</body>
</html>
```

## Exercícios

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Eventos de clique e teclado | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Validação em tempo real | ⭐⭐ Médio |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Canvas drawing com mouse | ⭐⭐ Médio |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Drag and drop | ⭐⭐⭐ Difícil |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Jogo da Velha | ⭐⭐⭐ Difícil |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Carrossel interativo | ⭐⭐⭐ Difícil |
