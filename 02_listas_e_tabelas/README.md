# Módulo 02 — Listas e Tabelas

## O que você vai aprender

Listas e tabelas são elementos essenciais para organizar informações na web. Neste módulo, você vai aprender a criar listas ordenadas, não ordenadas e tabelas com dados reais.

## Teoria

### Listas Não Ordenadas (ul)

Para listas onde a ordem não importa (como uma lista de compras):

```html
<ul>
    <li>Arroz</li>
    <li>Feijão</li>
    <li>Macarrão</li>
</ul>
```

### Listas Ordenadas (ol)

Para listas onde a ordem importa (como um ranking):

```html
<ol>
    <li>Ouro</li>
    <li>Prata</li>
    <li>Bronze</li>
</ol>
```

### Listas Aninhadas

Você pode misturar listas dentro de listas:

```html
<ul>
    <li>Lanches
        <ul>
            <li>Hambúrguer</li>
            <li>Pizza</li>
        </ul>
    </li>
    <li>Bebidas
        <ul>
            <li>Guaraná</li>
            <li>Suco de Laranja</li>
        </ul>
    </li>
</ul>
```

### Tabelas HTML

Tabelas organizam dados em linhas e colunas:

```html
<table>
    <thead>
        <tr>
            <th>Nome</th>
            <th>Nota</th>
            <th>Situação</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Maria</td>
            <td>9.5</td>
            <td>Aprovada</td>
        </tr>
        <tr>
            <td>João</td>
            <td>6.0</td>
            <td>Aprovado</td>
        </tr>
    </tbody>
</table>
```

### Exemplo Completo — Cardápio de Lanchonete

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cardápio - Lanchonete do Zé</title>
</head>
<body>
    <h1>Lanchonete do Zé</h1>

    <h2>🍔 Lanches</h2>
    <ul>
        <li>X-Burger — R$ 15,00</li>
        <li>X-Egg — R$ 17,00</li>
        <li>X-Bacon — R$ 18,00</li>
    </ul>

    <h2>🥤 Bebidas</h2>
    <ul>
        <li>Guaraná — R$ 5,00</li>
        <li>Coca-Cola — R$ 6,00</li>
        <li>Água — R$ 3,00</li>
    </ul>

    <h2>📊 Ranking dos Mais Pedidos</h2>
    <table>
        <thead>
            <tr>
                <th>Posição</th>
                <th>Item</th>
                <th>Pedidos no Mês</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1º</td>
                <td>X-Burger</td>
                <td>350</td>
            </tr>
            <tr>
                <td>2º</td>
                <td>Guaraná</td>
                <td>280</td>
            </tr>
            <tr>
                <td>3º</td>
                <td>X-Bacon</td>
                <td>210</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

## Exercícios

| Exercício | Arquivo | Tema | Dificuldade |
|-----------|---------|------|-------------|
| 01 | [exercicio_01.txt](exercicio_01.txt) | Lista de compras | ⭐ Fácil |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Ranking e lista ordenada | ⭐ Fácil |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Tabela de notas | ⭐ Fácil |
| 04 | [exercicio_04.txt](exercicio_04.txt) | Tabela de games | ⭐⭐ Médio |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Lista aninhada de playlists | ⭐⭐ Médio |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Cardápio completo | ⭐⭐ Médio |
