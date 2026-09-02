# Módulo 03 — CSS Fundamentos

## O que você vai aprender

CSS (Cascading Style Sheets) é a linguagem que dá estilo e cor às páginas web. Neste módulo, você vai aprender seletores, cores, fontes, box model e display — a base de todo design web.

## Teoria

### O que é CSS?

Enquanto HTML organiza o **conteúdo** (títulos, parágrafos, imagens), CSS cuida da **aparência** (cores, fontes, espaçamento, posicionamento).

### Formas de Incluir CSS

**1. CSS Interno (no HEAD):**
```html
<head>
    <style>
        h1 {
            color: blue;
        }
    </style>
</head>
```

**2. CSS Externo (arquivo separado):**
```html
<head>
    <link rel="stylesheet" href="estilo.css">
</head>
```

### Seletores Básicos

```css
/* Seletor por elemento */
h1 { color: red; }

/* Seletor por classe */
.destaque { background-color: yellow; }

/* Seletor por id */
#principal { font-size: 24px; }

/* Seletor múltiplo */
h1, h2, h3 { font-family: Arial; }
```

### Cores

```css
/* Nomes */
color: red;
color: blue;

/* Hexadecimal */
color: #FF5733;
background-color: #333333;

/* RGB */
color: rgb(255, 87, 51);
background-color: rgba(0, 0, 0, 0.5); /* com transparência */
```

### Fontes e Texto

```css
.fonte-grande { font-size: 24px; }
.negrito { font-weight: bold; }
.italico { font-style: italic; }
.centralizado { text-align: center; }
.sublinhado { text-decoration: underline; }
.caserneira { font-family: 'Arial', sans-serif; }
```

### Box Model (Modelo de Caixa)

Todo elemento HTML é uma "caixa" com 4 camadas:

```
┌─────────────────────────────┐
│          MARGIN             │
│  ┌───────────────────────┐  │
│  │       BORDER          │  │
│  │  ┌─────────────────┐  │  │
│  │  │     PADDING     │  │  │
│  │  │  ┌───────────┐  │  │  │
│  │  │  │  CONTEÚDO │  │  │  │
│  │  │  └───────────┘  │  │  │
│  │  └─────────────────┘  │  │
│  └───────────────────────┘  │
└─────────────────────────────┘
```

```css
.caixa {
    width: 200px;
    padding: 20px;
    border: 2px solid black;
    margin: 10px;
}
```

### Display

```css
display: block;      /* Ocupa linha inteira (como div, h1, p) */
display: inline;     /* Só ocupa o espaço do conteúdo (como a, span) */
display: inline-block; /* Inline mas aceita width/height */
display: none;       /* Esconde o elemento */
```

### Exemplo Completo

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Perfil Estilizado</title>
    <style>
        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 20px;
        }

        h1 {
            color: #333;
            text-align: center;
        }

        .card {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            max-width: 400px;
            margin: 20px auto;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .card h2 {
            color: #0077ff;
            margin-top: 0;
        }

        .tag {
            display: inline-block;
            background-color: #0077ff;
            color: white;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 12px;
            margin: 2px;
        }
    </style>
</head>
<body>
    <h1>Maria Silva</h1>
    <div class="card">
        <h2>Desenvolvedora Front-End</h2>
        <p>Aprendendo HTML, CSS e JavaScript no Laboratório Tech Social.</p>
        <span class="tag">HTML</span>
        <span class="tag">CSS</span>
        <span class="tag">JavaScript</span>
    </div>
</body>
</html>
```

## Exercícios

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Cores e fontes | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Classes e IDs | ⭐ Fácil |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Box model | ⭐⭐ Médio |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Display e alinhamento | ⭐⭐ Médio |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Card estilizado | ⭐⭐ Médio |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Página completa estilizada | ⭐⭐⭐ Difícil |
