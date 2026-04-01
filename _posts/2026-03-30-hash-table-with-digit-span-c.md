---
layout: post
title: "Hash adaptativa baseada nos dados (em C)"
date: 2026-03-30
categories: portfolio
mathjax: false
tags: [C, Data Structures]
image: /assets/images/umbrellan.png
github: https://github.com/natamleao/Hash-Table
excerpt: "Uma variação de tabela hash que escolhe o índice com base na distribuição dos próprios dados."
---

## Ideia

Em uma *tabela hash* tradicional, você define uma função e torce pra distribuição ser boa.

Aqui a tentativa foi inverter isso:

> deixar os próprios dados influenciarem a função de *hashing*

---

## O que foi feito

Implementei uma *tabela hash* em C com:

- *encadeamento* (*chaining*) para colisões  
- análise prévia das chaves  
- escolha dinâmica de como gerar o índice  

Além disso, incluí um gerador de dados para testar o comportamento da distribuição.

---

## Como funciona

Antes de inserir os valores, o sistema olha para o conjunto de dados.

O processo é:

- quebrar os números em dígitos  
- observar como esses dígitos se distribuem por posição  
- medir qual posição é mais “equilibrada”  
- usar esse dígito como base do índice  

No fim, o índice ainda é simples:

```c
index = digit % capacity;
````

Mas o dígito escolhido não é fixo — depende dos dados.

---

## O ponto interessante

A função de *hash* deixa de ser totalmente fixa.

Ela passa a ser, de certa forma, **adaptativa ao conjunto de entrada**.

Isso não garante distribuição perfeita, mas em alguns casos pode reduzir colisões sem aumentar muito a complexidade.

---

## Limitações

Essa abordagem tem algumas restrições claras:

* depende da qualidade dos dados
* não se adapta depois da construção inicial
* não há redimensionamento da tabela
* o critério de “melhor dígito” é heurístico

Ou seja: funciona mais como experimento do que solução geral.

---

## Por que esse projeto

A ideia aqui foi explorar uma pergunta simples:

> dá pra melhorar *hashing* usando informação dos próprios dados?

Sem complicar demais a implementação.

---

## Código

O projeto completo está disponível [aqui](https://github.com/natamleao/Hash-Table).

---
