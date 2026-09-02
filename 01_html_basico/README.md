# Módulo 01 — HTML Básico

## O que você vai aprender

HTML (HyperText Markup Language) é a linguagem que estrutura todo conteúdo da web. Neste módulo, você vai aprender a criar sua primeira página web com todos os elementos fundamentais.

## Teoria

### O que é HTML?

HTML não é uma linguagem de programação — é uma **linguagem de marcação**. Ela usa "tags" (etiquetas) para dizer ao navegador como exibir o conteúdo.

### Estrutura Básica

Todo documento HTML começa com esta estrutura:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minha Primeira Página</title>
</head>
<body>
    <!-- Seu conteúdo vai aqui -->
</body>
</html>
```

### Tags de Cabeçalho (Headings)

```html
<h1>Título Principal</h1>  <!-- O mais importante -->
<h2>Subtítulo</h2>
<h3>Título Menor</h3>
<h4>Título ainda menor</h4>
<h5>Quase um texto normal</h5>
<h6>O menor título</h6>
```

### Parágrafos e Texto

```html
<p>Este é um parágrafo de texto. Pode ter várias linhas.</p>
<p>Outro parágrafo.</p>

<strong>Texto em negrito</strong>
<em>Texto em itálico</em>
<br>  <!-- Quebra de linha -->
```

### Links

```html
<a href="https://www.google.com">Ir para o Google</a>
<a href="outra-pagina.html">Ir para outra página</a>
<a href="https://www.google.com" target="_blank">Abrir em nova aba</a>
```

### Imagens

```html
<img src="foto.jpg" alt="Descrição da imagem" width="300">
<img src="https://exemplo.com/foto.png" alt="Imagem da internet">
```

### Exemplo Completo

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Perfil</title>
</head>
<body>
    <h1>Maria Silva</h1>
    <h2>Estudante de Programação</h2>
    <p>Olá! Meu nome é Maria e estou aprendendo a programar.</p>
    <p>Este site foi feito por mim usando HTML!</p>
    <h3>Meus Links Favoritos</h3>
    <a href="https://www.youtube.com">YouTube</a>
    <br>
    <a href="https://github.com">GitHub</a>
</body>
</html>
```

## Exercícios

Resolva os exercícios na ordem indicada. Crie um arquivo `.html` para cada um e abra no navegador.

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Primeira página HTML | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Headings e parágrafos | ⭐ Fácil |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Links e navegação | ⭐ Fácil |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Imagens e atributos | ⭐ Fácil |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Combinação de elementos | ⭐⭐ Médio |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Página completa pessoal | ⭐⭐ Médio |
