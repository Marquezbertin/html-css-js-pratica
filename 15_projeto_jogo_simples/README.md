# Módulo 15 — Projeto: Jogo Simples em Canvas

## O que você vai aprender

Crie um jogo usando HTML5 Canvas e JavaScript puro. Neste projeto, você vai construir o clássico Pong (ou Snake) — entendendo conceitos de game loop, colisão, entrada do jogador e renderização.

## Teoria

### O que é Canvas?

Canvas é um elemento HTML que permite desenhar gráficos via JavaScript:

```javascript
let canvas = document.getElementById("gameCanvas");
let ctx = canvas.getContext("2d");

// Desenhar retângulo
ctx.fillStyle = "white";
ctx.fillRect(10, 10, 50, 50);

// Desenhar círculo
ctx.beginPath();
ctx.arc(100, 100, 10, 0, Math.PI * 2);
ctx.fill();

// Limpar tela
ctx.clearRect(0, 0, canvas.width, canvas.height);
```

### Game Loop

Todo jogo tem um loop que atualiza e desenha a tela repetidamente:

```javascript
function gameLoop() {
    atualizar();  // Mover elementos, verificar colisões
    desenhar();   // Redesenhar tudo na tela
    requestAnimationFrame(gameLoop); // Chamar próxima frame
}
requestAnimationFrame(gameLoop);
```

### Controles do Teclado

```javascript
let teclas = {};

document.addEventListener("keydown", (e) => {
    teclas[e.key] = true;
});

document.addEventListener("keyup", (e) => {
    teclas[e.key] = false;
});

// No game loop:
if (teclas["ArrowUp"]) {
    jogador.y -= velocidade;
}
if (teclas["ArrowDown"]) {
    jogador.y += velocidade;
}
```

### Conceitos de Colisão

```javascript
function verificarColisao(a, b) {
    return a.x < b.x + b.largura &&
           a.x + a.largura > b.x &&
           a.y < b.y + b.altura &&
           a.y + a.altura > b.y;
}
```

## Guia do Projeto — Pong

### Estrutura de Arquivos

```
15_projeto_jogo_simples/
├── README.md
├── index.html
├── styles.css
├── game.js
├── exercicio_01.txt
├── exercicio_02.txt
├── exercicio_03.txt
├── exercicio_04.txt
├── exercicio_05.txt
└── exercicio_06.txt
```

## Exercícios

| Exercício | Arquivo | Tarefa | Dificuldade |
|-----------|---------|--------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Estrutura Canvas + game loop | ⭐⭐ Médio |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Raquetes e controles | ⭐⭐ Médio |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Bola e colisões | ⭐⭐⭐ Difícil |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Placar e regras | ⭐⭐⭐ Difícil |
| 05 | [exercicio_05.txt](exercicio_05.txt) | IA do oponente | ⭐⭐⭐ Difícil |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Polish e efeitos | ⭐⭐⭐⭐ Expert |
