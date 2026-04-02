---
layout: post
title: "Hash adaptativa baseada nos dados"
date: 2026-03-30
categories: portfolio
mathjax: false
tags: [C, Data Structures]
image: /assets/images/umbrellan.png
github: https://github.com/natamleao/Hash-Table
excerpt: "Uma variação de tabela hash que escolhe o índice com base na distribuição dos próprios dados."
---

## De onde veio a ideia

Tabela *hash* normalmente começa com uma decisão fixa: você define uma função e trabalha em cima dela.

Aqui eu quis fazer um pequeno desvio desse padrão — não mudando a estrutura, mas a forma de escolher a função.

A motivação foi simples: antes de aplicar a função, olhar minimamente para os dados.

---

## O método

A abordagem usada aqui não é nova.

Ela segue uma linha conhecida em *hashing*: usar propriedades da distribuição das chaves para tentar escolher uma função que se comporte melhor naquele contexto.

No caso, a escolha foi trabalhar com **análise de dígitos**:

* decompor os números em dígitos
* observar a frequência de cada dígito por posição
* comparar com uma distribuição ideal (uniforme)
* escolher a posição mais “equilibrada”

Isso gera um critério simples:
usar o dígito menos enviesado como base para o índice.

Não é uma função universal, nem perfeita — é uma heurística baseada no conjunto de entrada.

---

## Por que isso faz sentido

Nem todo dígito carrega a mesma informação.

Dependendo do conjunto, alguns dígitos são praticamente inúteis (muito repetidos), enquanto outros distribuem melhor.

A ideia é justamente evitar escolhas ruins logo de cara.

Em vez de usar, por exemplo, sempre o último dígito, deixar os dados indicarem qual posição tende a espalhar melhor os valores.

---

## O que muda na prática

A função final continua simples:

```c
index = digit % capacity;
```

Nada sofisticado.

A diferença é que o *digit* não é fixo — ele é escolhido com base em uma análise prévia.

Isso mantém a implementação leve, mas introduz um pequeno grau de adaptação.

---

## Limitações 

Esse tipo de abordagem tem limites claros:

* depende completamente do conjunto inicial
* não reage a mudanças depois
* o critério de “melhor distribuição” é aproximado
* não substitui funções de *hash* mais robustas

Ou seja, não é solução geral — é uma variação pontual.

---

## Por que explorar isso

O objetivo aqui não foi propor algo novo, mas tornar explícita uma ideia que normalmente fica implícita:

> a escolha da função de *hash* pode (e talvez devesse) considerar os dados

Mesmo que de forma simples.

Implementar isso em C, de maneira direta, foi mais um exercício de exploração do que de otimização.

---

## Fechamento

Esse projeto fica num meio-termo interessante:

não muda a estrutura clássica, mas também não aceita completamente a rigidez dela.

É só um pequeno ajuste de perspectiva —
de função fixa para função influenciada pelos dados.

E às vezes esse tipo de ajuste já abre espaço pra pensar diferente.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Hash-Table).

---
