# Módulo 04 — CSS Layout (Flexbox e Grid)

## O que você vai aprender

Layout é como os elementos se posicionam na página. Neste módulo, você vai aprender as duas ferramentas mais poderosas do CSS moderno: Flexbox e Grid, além de responsividade e media queries.

## Teoria

### Flexbox — Layout em uma Dimensão

Flexbox organiza itens em uma **linha** (horizontal ou vertical).

```css
.container {
    display: flex;
    justify-content: space-between; /* Espaço entre os itens */
    align-items: center;            /* Alinha verticalmente */
    gap: 20px;                      /* Espaço entre itens */
}
```

**Propriedades de Flexbox:**

| Propriedade | Valores | Efeito |
|------------|---------|--------|
| `flex-direction` | row, column | Direção dos itens |
| `justify-content` | center, space-between, space-around | Alinhamento horizontal |
| `align-items` | center, flex-start, flex-end | Alinhamento vertical |
| `flex-wrap` | wrap, nowrap | Quebra de linha |

**Exemplo — Navbar com Flexbox:**
```css
nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 30px;
    background: #333;
}

nav a {
    color: white;
    text-decoration: none;
}
```

**Exemplo — Cards em linha:**
```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1;
    min-width: 250px;
    padding: 20px;
}
```

### CSS Grid — Layout em Duas Dimensões

Grid organiza itens em **linhas e colunas** simultaneamente.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr; /* 3 colunas iguais */
    gap: 20px;
}
```

**Exemplo — Grid Simples:**
```css
.grid {
    display: grid;
    grid-template-columns: 1fr 2fr; /* 1ª coluna menor, 2ª maior */
    gap: 15px;
}
```

**Exemplo — Grid Responsivo:**
```css
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
}
```

### Responsividade e Media Queries

Para adaptar o layout a diferentes tamanhos de tela:

```css
/* Estilo padrão (celular) */
.container {
    display: flex;
    flex-direction: column;
}

/* Tablet (a partir de 768px) */
@media (min-width: 768px) {
    .container {
        flex-direction: row;
    }
}

/* Desktop (a partir de 1024px) */
@media (min-width: 1024px) {
    .container {
        padding: 0 100px;
    }
}
```

### Exemplo Completo

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Layout Responsivo</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 30px;
            background: #1a1a2e;
            color: white;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            margin-left: 20px;
        }

        .hero {
            text-align: center;
            padding: 80px 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            padding: 40px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .card {
            background: white;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        footer {
            text-align: center;
            padding: 30px;
            background: #1a1a2e;
            color: white;
        }
    </style>
</head>
<body>
    <nav>
        <div class="logo">MeuSite</div>
        <div class="nav-links">
            <a href="#">Início</a>
            <a href="#">Sobre</a>
            <a href="#">Contato</a>
        </div>
    </nav>
    <div class="hero">
        <h1>Bem-vindo!</h1>
        <p>Este é um exemplo de layout responsivo</p>
    </div>
    <div class="cards">
        <div class="card"><h3>Card 1</h3><p>Conteúdo...</p></div>
        <div class="card"><h3>Card 2</h3><p>Conteúdo...</p></div>
        <div class="card"><h3>Card 3</h3><p>Conteúdo...</p></div>
    </div>
    <footer>© 2024 Laboratório Tech Social</footer>
</body>
</html>
```

## Exercícios

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Flexbox básico | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Navbar com Flexbox | ⭐⭐ Médio |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Grid de cards | ⭐⭐ Médio |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Media queries | ⭐⭐ Médio |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Layout completo responsivo | ⭐⭐⭐ Difícil |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Dashboard responsivo | ⭐⭐⭐ Difícil |
