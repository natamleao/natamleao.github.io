---
layout: post
title: "Comparando preços e organizando dados em C++"
date: 2026-03-14
categories: portfolio
mathjax: false
tags: [C++, Data Structures]
image: /assets/images/price-comparison-cpp-thumbnail.png
github: https://github.com/natamleao/Price-Comparison-CPP
excerpt: "Um pequeno sistema em C++ para organizar e comparar preços usando lista encadeada."
---

## Ideia

Queria sair um pouco de implementações isoladas e montar algo mais próximo de um sistema, mesmo que simples.

A ideia foi direta:  
> cadastrar itens, manipular esses dados e tirar alguma conclusão útil deles.

No caso, comparar preços.

---

## O que foi feito

Implementei um sistema em **C++** baseado em **lista encadeada**, onde é possível:

- inserir itens com identificador e preço  
- atualizar informações  
- remover elementos  
- listar os dados  
- avaliar se um preço compensa ou não  

Tudo rodando em linha de comando, sem abstrações além do necessário.

---

## Estrutura escolhida

Usei uma lista encadeada simples.

Não é a estrutura mais performática para tudo, mas tem duas vantagens aqui:

- controle direto da memória  
- flexibilidade para inserção e remoção  

Para esse tipo de sistema pequeno, faz sentido.

---

## Uso de C++

Diferente de implementações em C, aqui usei **classes** para organizar o código.

Isso ajudou a:

- agrupar dados e comportamento  
- evitar funções soltas  
- deixar a estrutura mais clara  

Sem exagerar — só o suficiente para melhorar a organização.

---

## Um detalhe interessante

Mesmo sendo um sistema simples, ele já tem um fluxo completo:

- entrada de dados  
- armazenamento  
- manipulação  
- processamento  
- saída  

Isso muda a forma de pensar o código.  
Não é mais só “fazer funcionar”, mas manter tudo coerente.

---

## Por que esse projeto

A ideia aqui não era complexidade, e sim:

- reforçar estruturas de dados em um contexto real  
- praticar organização de código em C++  
- sair do padrão “função isolada” e pensar em fluxo  

---

## Código 

O projeto completo está disponível [aqui](https://github.com/natamleao/Price-Comparison-CPP).

---
