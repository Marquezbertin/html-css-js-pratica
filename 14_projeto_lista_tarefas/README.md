# Módulo 14 — Projeto: Lista de Tarefas (Todo App)

## O que você vai aprender

Crie um aplicativo completo de lista de tarefas (To-Do List) com funcionalidades CRUD, persistência com localStorage e uma interface moderna. Este projeto consolida HTML, CSS e JavaScript.

## Teoria

### O que é um CRUD?

CRUD significa Create (criar), Read (ler), Update (atualizar) e Delete (deletar). É a base de qualquer aplicação que gerencia dados.

### localStorage

O localStorage permite salvar dados no navegador que persistem mesmo após fechar a página:

```javascript
// Salvar
localStorage.setItem("tarefas", JSON.stringify(tarefas));

// Carregar
let dados = JSON.parse(localStorage.getItem("tarefas")) || [];

// Remover
localStorage.removeItem("tarefas");
```

### Estrutura de Dados

```javascript
let tarefa = {
    id: 1,
    texto: "Estudar JavaScript",
    concluida: false,
    data: "2024-01-15",
    prioridade: "alta"
};
```

## Guia do Projeto

### Estrutura de Arquivos

```
14_projeto_lista_tarefas/
├── README.md
├── index.html
├── styles.css
├── app.js
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
| 01 | [exercicio_01.txt](exercicio_01.txt) | Estrutura HTML + CSS | ⭐⭐ Médio |
| 02 | [exercicio_02.txt](exercicio_02.txt) | Adicionar tarefas | ⭐⭐ Médio |
| 03 | [exercicio_03.txt](exercicio_03.txt) | Concluir e remover | ⭐⭐ Médio |
| 04 | [exercicio_04.txt](exercicio_04.txt) | localStorage | ⭐⭐⭐ Difícil |
| 05 | [exercicio_05.txt](exercicio_05.txt) | Filtros e contadores | ⭐⭐⭐ Difícil |
| 06 | [exercicio_06.txt](exercicio_06.txt) | Funcionalidades extras | ⭐⭐⭐⭐ Expert |
