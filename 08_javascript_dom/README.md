# Módulo 08 — JavaScript e o DOM

## O que você vai aprender

DOM (Document Object Model) é como o JavaScript acessa e modifica o HTML. Neste módulo, você vai aprender a selecionar elementos, alterar conteúdo, estilos e estrutura da página dinamicamente.

## Teoria

### O que é o DOM?

O DOM é uma representação da página HTML como uma árvore de objetos. Cada tag HTML vira um "nó" que o JavaScript pode manipular.

```
document
├── html
│   ├── head
│   │   ├── meta
│   │   └── title
│   └── body
│       ├── h1
│       ├── p
│       └── div
│           └── button
```

### Selecionar Elementos

```javascript
// Por ID (retorna UM elemento)
let titulo = document.getElementById("titulo");

// Por classe (retorna LISTA de elementos)
let cards = document.querySelectorAll(".card");

// Por tag (retorna LISTA de elementos)
let paragrafos = document.querySelectorAll("p");

// Por seletor CSS (retorna PRIMEIRO elemento)
let primeiro = document.querySelector(".card");

// Por seletor CSS (retorna TODOS)
let todos = document.querySelectorAll(".card");
```

### Alterar Conteúdo

```javascript
// Texto
elemento.innerText = "Novo texto";
elemento.textContent = "Novo texto (inclui espaços ocultos)";

// HTML
elemento.innerHTML = "<strong>Texto em negrito</strong>";

// Valor de input
input.value = "Novo valor";
```

### Alterar Estilos

```javascript
// Propriedade style
elemento.style.color = "red";
elemento.style.backgroundColor = "blue";
elemento.style.fontSize = "24px";
elemento.style.padding = "10px";
elemento.style.borderRadius = "8px";
```

### Adicionar/Remover Classes

```javascript
// Adicionar classe
elemento.classList.add("ativo");

// Remover classe
elemento.classList.remove("ativo");

// Alternar classe (toggle)
elemento.classList.toggle("ativo");

// Verificar se tem a classe
if (elemento.classList.contains("ativo")) {
    console.log("Está ativo!");
}
```

### Criar e Inserir Elementos

```javascript
// Criar novo elemento
let novoElemento = document.createElement("div");
novoElemento.innerText = "Olá, mundo!";
novoElemento.classList.add("card");

// Inserir no final
document.body.appendChild(novoElemento);

// Inserir antes de outro elemento
let referencia = document.getElementById("existente");
document.body.insertBefore(novoElemento, referencia);

// Remover elemento
elemento.remove();
// ou
elemento.parentNode.removeChild(elemento);
```

### Atributos

```javascript
// Ler atributo
let src = imagem.getAttribute("src");

// Definir atributo
imagem.setAttribute("src", "nova-foto.jpg");
imagem.setAttribute("alt", "Nova descrição");

// Remover atributo
imagem.removeAttribute("title");
```

### Exemplo Completo — Lista de Compras Interativa

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lista de Compras</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body {
            font-family: Arial, sans-serif;
            background: #f5f5f5;
            padding: 20px;
        }
        .container {
            max-width: 500px;
            margin: 0 auto;
            background: white;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        h1 { text-align: center; margin-bottom: 20px; color: #333; }
        .input-group {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
        }
        input {
            flex: 1;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-size: 16px;
        }
        button {
            padding: 10px 20px;
            background: #0077ff;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
        }
        button:hover { background: #0055cc; }
        .item {
            display: flex;
            align-items: center;
            padding: 10px;
            border-bottom: 1px solid #eee;
        }
        .item.comprado {
            text-decoration: line-through;
            opacity: 0.5;
        }
        .item .texto { flex: 1; }
        .item .remover {
            background: #ff4444;
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 4px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🛒 Lista de Compras</h1>
        <div class="input-group">
            <input type="text" id="itemInput" placeholder="Adicionar item...">
            <button onclick="adicionarItem()">Adicionar</button>
        </div>
        <div id="lista"></div>
    </div>

    <script>
        let itens = [];

        function adicionarItem() {
            let input = document.getElementById("itemInput");
            let texto = input.value.trim();
            if (texto === "") return;

            itens.push({ texto: texto, comprado: false });
            input.value = "";
            renderizar();
        }

        function toggleItem(index) {
            itens[index].comprado = !itens[index].comprado;
            renderizar();
        }

        function removerItem(index) {
            itens.splice(index, 1);
            renderizar();
        }

        function renderizar() {
            let html = "";
            for (let i = 0; i < itens.length; i++) {
                let classe = itens[i].comprado ? "item comprado" : "item";
                html += '<div class="' + classe + '">';
                html += '<span class="texto" onclick="toggleItem(' + i + ')">' + itens[i].texto + '</span>';
                html += '<button class="remover" onclick="removerItem(' + i + ')">X</button>';
                html += '</div>';
            }
            document.getElementById("lista").innerHTML = html;
        }
    </script>
</body>
</html>
```

## Exercícios

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Selecionar e alterar elementos | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Criar e remover elementos | ⭐⭐ Médio |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Alternar classes CSS | ⭐⭐ Médio |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Modo escuro/claro | ⭐⭐ Médio |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Contador interativo | ⭐⭐ Médio |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Lista de tarefas DOM | ⭐⭐⭐ Difícil |
