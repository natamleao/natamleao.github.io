---
layout: post
title: "Gerenciando alunos e persistindo dados em C"
date: 2026-03-24
categories: portfolio
mathjax: false
tags: [C, Data Structures]
image: /assets/images/student-management-c-thumbnail.png
github: https://github.com/natamleao/Student-Management-System
excerpt: "Sistema em C com lista duplamente encadeada e persistência em arquivo binário."
---

## Ideia

Queria ir além de estruturas isoladas e montar algo mais próximo de um sistema.

Nesse caso:  
> armazenar dados, manipular em memória e persistir de forma consistente

Sem depender de bibliotecas externas.

---

## O que foi feito

Implementei um gerenciador de alunos em C que permite:

- cadastrar e remover registros  
- buscar por matrícula  
- listar dados  
- manter persistência automática em arquivo  

Cada aluno possui informações básicas e um campo adicional (livro favorito), adicionando um pouco mais de estrutura aos dados.

---

## Estrutura escolhida

Usei uma **lista duplamente encadeada**.

Isso facilita:

- inserções nas extremidades  
- remoções sem percorrer toda a lista  
- navegação nos dois sentidos  

Não é a estrutura mais simples, mas deixa as operações mais equilibradas.

---

## Persistência

Os dados são armazenados em **arquivo binário**.

Aqui a ideia foi evitar parsing de texto e trabalhar direto com bytes.

Isso exige mais cuidado:

- definir um formato consistente  
- serializar strings manualmente  
- reconstruir estruturas na leitura  

Mas em troca, o acesso fica mais direto.

---

## Um ponto importante

Quando você mistura:

- memória dinâmica  
- estruturas encadeadas  
- escrita em arquivo  

os erros ficam mais fáceis de aparecer.

Esse tipo de projeto força mais atenção em:

- alocação e liberação correta  
- cópia de dados (especialmente strings)  
- consistência entre leitura e escrita  

---

## Por que esse projeto

A ideia aqui foi:

- trabalhar com dados além do tempo de execução  
- entender melhor serialização manual  
- aproximar o código de algo mais próximo de um sistema real  

---

## Código

O projeto completo está disponível [aqui](https://github.com/natamleao/Student-Management-System)

---
