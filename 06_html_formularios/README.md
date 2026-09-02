# Módulo 06 — HTML Formulários

## O que você vai aprender

Formulários são essenciais para coletar dados dos usuários. Neste módulo, você vai aprender todos os tipos de input, validação, select, textarea e como criar formulários funcionais e acessíveis.

## Teoria

### Estrutura Básica de um Formulário

```html
<form action="/enviar" method="POST">
    <label for="nome">Nome:</label>
    <input type="text" id="nome" name="nome" placeholder="Seu nome">

    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email" required>

    <button type="submit">Enviar</button>
</form>
```

### Tipos de Input

```html
<!-- Texto -->
<input type="text">          <!-- Texto simples -->
<input type="password">      <!-- Senha (esconde os caracteres) -->
<input type="email">         <!-- E-mail (valida automaticamente) -->
<input type="number">        <!-- Números -->
<input type="tel">           <!-- Telefone -->
<input type="url">           <!-- URL -->
<input type="search">        <!-- Campo de busca -->
<input type="date">          <!-- Seletor de data -->
<input type="time">          <!-- Seletor de hora -->
<input type="color">         <!-- Seletor de cor -->

<!-- Outros -->
<input type="checkbox">      <!-- Caixa de seleção múltipla -->
<input type="radio">         <!-- Seleção única -->
<input type="range">         <!-- Slider -->
<input type="file">          <!-- Upload de arquivo -->
<input type="hidden">        <!-- Campo escondido -->
```

### Validação com HTML

```html
<input type="text" required>              <!-- Obrigatório -->
<input type="email" required>             <!-- Valida formato e-mail -->
<input type="number" min="0" max="100">  <!-- Valor entre 0 e 100 -->
<input type="text" minlength="3">        <!-- Mínimo 3 caracteres -->
<input type="text" maxlength="50">       <!-- Máximo 50 caracteres -->
<input type="text" pattern="[A-Za-z]{3}"> <!-- Padrão regex -->
```

### Select, Textarea e Outros

```html
<!-- Select (menu suspenso) -->
<select name="estado" id="estado">
    <option value="">Selecione...</option>
    <option value="SP">São Paulo</option>
    <option value="RJ">Rio de Janeiro</option>
    <option value="MG">Minas Gerais</option>
</select>

<!-- Textarea (área de texto) -->
<textarea name="mensagem" rows="5" cols="40" placeholder="Sua mensagem..."></textarea>

<!-- Fieldset e Legend -->
<fieldset>
    <legend>Dados Pessoais</legend>
    <label for="nome">Nome:</label>
    <input type="text" id="nome" name="nome">
</fieldset>
```

### Exemplo Completo — Formulário de Cadastro

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cadastro</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body {
            font-family: Arial, sans-serif;
            background: #f0f0f0;
            display: flex;
            justify-content: center;
            padding: 40px 20px;
        }
        .form-container {
            background: white;
            padding: 30px;
            border-radius: 12px;
            width: 100%;
            max-width: 500px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        h2 { margin-bottom: 20px; color: #333; }
        .grupo {
            margin-bottom: 15px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: #555;
        }
        input, select, textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-size: 14px;
        }
        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: #0077ff;
            box-shadow: 0 0 5px rgba(0,119,255,0.3);
        }
        button {
            width: 100%;
            padding: 12px;
            background: #0077ff;
            color: white;
            border: none;
            border-radius: 6px;
            font-size: 16px;
            cursor: pointer;
        }
        button:hover { background: #0055cc; }
    </style>
</head>
<body>
    <div class="form-container">
        <h2>Criar Conta</h2>
        <form>
            <div class="grupo">
                <label for="nome">Nome Completo</label>
                <input type="text" id="nome" name="nome" required placeholder="Maria Silva">
            </div>
            <div class="grupo">
                <label for="email">E-mail</label>
                <input type="email" id="email" name="email" required placeholder="maria@email.com">
            </div>
            <div class="grupo">
                <label for="senha">Senha</label>
                <input type="password" id="senha" name="senha" required minlength="6">
            </div>
            <div class="grupo">
                <label for="nascimento">Data de Nascimento</label>
                <input type="date" id="nascimento" name="nascimento" required>
            </div>
            <div class="grupo">
                <label for="estado">Estado</label>
                <select id="estado" name="estado" required>
                    <option value="">Selecione...</option>
                    <option value="SP">São Paulo</option>
                    <option value="RJ">Rio de Janeiro</option>
                    <option value="MG">Minas Gerais</option>
                </select>
            </div>
            <div class="grupo">
                <label for="bio">Bio (opcional)</label>
                <textarea id="bio" name="bio" rows="3" placeholder="Conte sobre você..."></textarea>
            </div>
            <div class="grupo">
                <label>
                    <input type="checkbox" name="termos" required>
                    Aceito os termos de uso
                </label>
            </div>
            <button type="submit">Cadastrar</button>
        </form>
    </div>
</body>
</html>
```

## Exercícios

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Formulário de login | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Formulário de cadastro | ⭐⭐ Médio |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Formulário com validação | ⭐⭐ Médio |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Formulário de pesquisa avançado | ⭐⭐ Médio |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Formulário de enquete/poll | ⭐⭐⭐ Difícil |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Formulário completo multi-step | ⭐⭐⭐ Difícil |
