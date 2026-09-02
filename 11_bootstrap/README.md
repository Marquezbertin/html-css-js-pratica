# Módulo 11 — Bootstrap

## O que você vai aprender

Bootstrap é a biblioteca CSS mais popular do mundo. Neste módulo, você vai aprender a usar o grid system, componentes prontos, navbar, cards, formulários e como criar sites profissionais rapidamente.

## Teoria

### Como usar Bootstrap

**Via CDN (mais fácil):**
```html
<head>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
```

### Grid System (12 colunas)

```html
<div class="container">
    <div class="row">
        <div class="col-md-4">1/3 da tela</div>
        <div class="col-md-4">1/3 da tela</div>
        <div class="col-md-4">1/3 da tela</div>
    </div>
</div>
```

**Breakpoints do Bootstrap:**
- `col-` : todos os tamanhos (mobile-first)
- `col-sm-` : ≥576px
- `col-md-` : ≥768px
- `col-lg-` : ≥992px
- `col-xl-` : ≥1200px

### Componentes Principais

**Navbar:**
```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
        <a class="navbar-brand" href="#">MeuSite</a>
        <div class="navbar-nav">
            <a class="nav-link" href="#">Início</a>
            <a class="nav-link" href="#">Sobre</a>
            <a class="nav-link" href="#">Contato</a>
        </div>
    </div>
</nav>
```

**Cards:**
```html
<div class="card" style="width: 18rem;">
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
        <h5 class="card-title">Título</h5>
        <p class="card-text">Texto do card</p>
        <a href="#" class="btn btn-primary">Ver mais</a>
    </div>
</div>
```

**Botões:**
```html
<button class="btn btn-primary">Primário</button>
<button class="btn btn-danger">Perigo</button>
<button class="btn btn-outline-success">Sucesso Outline</button>
<button class="btn btn-lg btn-warning">Grande Atenção</button>
```

**Badges e Alerts:**
```html
<span class="badge bg-primary">Novo</span>
<span class="badge bg-danger">5</span>

<div class="alert alert-success">Sucesso!</div>
<div class="alert alert-warning">Atenção!</div>
```

**Formulários:**
```html
<div class="mb-3">
    <label class="form-label">Nome</label>
    <input type="text" class="form-control" placeholder="Seu nome">
</div>
<div class="mb-3">
    <label class="form-label">E-mail</label>
    <input type="email" class="form-control" placeholder="seu@email.com">
</div>
<button class="btn btn-primary">Enviar</button>
```

### Exemplo Completo

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MeuSite com Bootstrap</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>

<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
        <a class="navbar-brand" href="#">DevBlog</a>
        <div class="navbar-nav ms-auto">
            <a class="nav-link" href="#">Home</a>
            <a class="nav-link" href="#">Posts</a>
            <a class="nav-link" href="#">Sobre</a>
        </div>
    </div>
</nav>

<div class="bg-primary text-white text-center py-5">
    <div class="container">
        <h1>Bem-vindo ao DevBlog</h1>
        <p class="lead">Aprenda programação do zero</p>
        <a href="#" class="btn btn-light btn-lg">Começar Agora</a>
    </div>
</div>

<div class="container my-5">
    <h2 class="text-center mb-4">Cursos Populares</h2>
    <div class="row g-4">
        <div class="col-md-4">
            <div class="card h-100">
                <div class="card-body">
                    <h5 class="card-title">HTML & CSS</h5>
                    <p class="card-text">Aprenda a criar sites do zero.</p>
                    <span class="badge bg-success">Grátis</span>
                </div>
            </div>
        </div>
        <div class="col-md-4">
            <div class="card h-100">
                <div class="card-body">
                    <h5 class="card-title">JavaScript</h5>
                    <p class="card-text">Torne suas páginas interativas.</p>
                    <span class="badge bg-warning">Popular</span>
                </div>
            </div>
        </div>
        <div class="col-md-4">
            <div class="card h-100">
                <div class="card-body">
                    <h5 class="card-title">React</h5>
                    <p class="card-text">Interfaces modernas e rápidas.</p>
                    <span class="badge bg-info">Novo</span>
                </div>
            </div>
        </div>
    </div>
</div>

<footer class="bg-dark text-white text-center py-3">
    <p>&copy; 2024 Laboratório Tech Social</p>
</footer>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

## Exercícios

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Grid system | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Navbar responsiva | ⭐ Fácil |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Cards e botões | ⭐⭐ Médio |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Formulários Bootstrap | ⭐⭐ Médio |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Página completa | ⭐⭐⭐ Difícil |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Template multi-página | ⭐⭐⭐ Difícil |
