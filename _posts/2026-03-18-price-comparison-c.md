---
layout: post
title: "Comparando preços com controle manual em C"
date: 2026-03-18
categories: portfolio
mathjax: false
tags: [C, Data Structures]
image: /assets/images/price-comparison-c-thumbnail.png
github: https://github.com/natamleao/Price-Comparison-C
excerpt: "Sistema em C para manipulação e análise de preços com controle manual de memória."
---

## Ideia

Depois de implementar a versão em C++ (clique [aqui](https://natamleao.github.io/price-comparison-cpp/) para vê-la), quis voltar um passo e fazer o mesmo tipo de sistema em **C puro**.

Sem classes, sem abstrações — só ponteiros, structs e controle manual.

---

## O que foi feito

Um sistema simples para:

- inserir itens com identificador e preço  
- atualizar e remover dados  
- listar os elementos  
- avaliar os preços  

Tudo baseado em uma **lista encadeada**.

---

## Diferença principal

Aqui não tem encapsulamento.

Isso muda bastante coisa:

- os dados ficam expostos  
- a responsabilidade de organização é maior  
- o controle de memória precisa ser explícito  

Cada `malloc` e `free` importa.

---

## Estrutura

Usei uma lista encadeada simples.

Ela resolve bem o problema e mantém o código direto, sem estruturas auxiliares.

---

## Um ponto importante

Comparado com a versão em C++, esse código exige mais cuidado:

- não há proteção contra uso incorreto  
- erros de memória aparecem fácil  
- a organização depende mais de disciplina do que da linguagem  

Por outro lado, dá uma visão mais clara de como tudo funciona por baixo.

---

## Por que esse projeto

A ideia foi entender melhor a diferença prática entre:

- resolver um problema com abstração (C++)  
- resolver o mesmo problema com controle total (C)  

---

## Código

O projeto completo está disponível [aqui](https://github.com/natamleao/Price-Comparison-C)

---
