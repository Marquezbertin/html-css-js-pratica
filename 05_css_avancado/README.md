# Módulo 05 — CSS Avançado (Animações e Efeitos)

## O que você vai aprender

Neste módulo, você vai dar vida às suas páginas com animações, transições suaves, gradientes bonitos e efeitos de sombra profissionais.

## Teoria

### Transições

Transições fazem mudanças de estilo acontecerem **suavemente**:

```css
.botao {
    background-color: #0077ff;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    transition: all 0.3s ease;
}

.botao:hover {
    background-color: #0055cc;
    transform: scale(1.05);
}
```

**Propriedades de transição:**
```css
.elemento {
    transition: [propriedade] [duração] [função];
    transition: all 0.3s ease;           /* Todas as propriedades */
    transition: transform 0.5s ease-in-out; /* Só o transform */
    transition: background-color 0.2s, color 0.2s; /* Múltiplas */
}
```

### Animações com @keyframes

Animações são mais complexas que transições — você define estágios:

```css
@keyframes girar {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

@keyframes flutuar {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
}

.icone-girando {
    animation: girar 2s linear infinite;
}

 elemento-flutuando {
    animation: flutuar 3s ease-in-out infinite;
}
```

### Gradientes

```css
/* Linear */
.gradiente-1 {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

/* Radial */
.gradiente-2 {
    background: radial-gradient(circle, #ff6b6b, #556270);
}

/* Multi-stop */
.gradiente-3 {
    background: linear-gradient(to right, #ff6b6b, #feca57, #48dbfb, #ff9ff3);
}
```

### Sombras

```css
/* Sombra simples */
.sombra-1 {
    box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}

/* Sombra com deslocamento */
.sombra-2 {
    box-shadow: 5px 5px 15px rgba(0,0,0,0.3);
}

/* Sombra interna */
.sombra-3 {
    box-shadow: inset 0 2px 5px rgba(0,0,0,0.2);
}

/* Múltiplas sombras (efeito neon) */
.neon {
    text-shadow: 0 0 5px #0077ff, 0 0 10px #0077ff, 0 0 20px #0077ff;
}
```

### Transform

```css
/* Escala */
.escala:hover { transform: scale(1.1); }

/* Rotação */
.girar:hover { transform: rotate(45deg); }

/* Translação */
.mover:hover { transform: translateX(20px); }

/* Skew (inclinar) */
.inclinar:hover { transform: skewX(10deg); }

/* Múltiplas transformações */
.completo:hover { transform: scale(1.1) rotate(5deg); }
```

### Exemplo Completo — Card com Efeitos

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exemplo de Efeitos CSS</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            font-family: Arial, sans-serif;
        }

        .card {
            background: white;
            width: 300px;
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
        }

        .card .avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 40px;
            color: white;
            transition: transform 0.3s ease;
        }

        .card:hover .avatar {
            transform: scale(1.1) rotate(360deg);
        }

        .btn {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 15px;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .btn:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.5);
        }
    </style>
</head>
<body>
    <div class="card">
        <div class="avatar">🎮</div>
        <h2>Jogador Pro</h2>
        <p>Nível máximo desbloqueado</p>
        <button class="btn">Ver Perfil</button>
    </div>
</body>
</html>
```

## Exercícios

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Transições em botões | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Hover effects em cards | ⭐⭐ Médio |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Animações com keyframes | ⭐⭐ Médio |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Gradientes e textos neon | ⭐⭐ Médio |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Página com efeitos combinados | ⭐⭐⭐ Difícil |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Loading screen animada | ⭐⭐⭐ Difícil |
