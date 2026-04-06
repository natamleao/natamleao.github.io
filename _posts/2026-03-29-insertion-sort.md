---
layout: post
title: "Insertion Sort e o que acontece quando você mede"
date: 2026-03-30
categories: portfolio
mathjax: true
tags: [C, Algorithms, Sorting]
image: /assets/images/insertion-sort.png
github: https://github.com/natamleao/Insertion-Sort
excerpt: "Implementação de Insertion Sort em C com medição de tempo para observar o comportamento na prática."
---

## O ponto de partida

*Insertion Sort* é um daqueles algoritmos que todo mundo conhece cedo.

Simples, direto, quase intuitivo.
Você percorre o *array* e vai inserindo cada elemento na posição correta.

Então a motivação aqui não foi “entender como funciona”.

Foi outra:

> sair do nível teórico e observar o comportamento quando você mede de verdade

---

## Implementar é o básico

A implementação segue o caminho esperado:

* *array* dinâmico para armazenar os dados
* percurso sequencial
* inserção na parte já ordenada
* ordenação *in-place*

Nada além do necessário.

E isso é intencional — quanto mais simples a base, mais claro fica o comportamento do algoritmo.

---

## Onde começa a ficar interessante

A diferença aqui foi tratar a medição como parte central.

Usei `clock_gettime` com `CLOCK_MONOTONIC` para capturar tempo de execução real.

Porque dizer que o algoritmo é $O(n^2)$ é fácil.

> o que importa é ver o que isso significa quando você roda de fato

---

## O que muda quando você mede

Com poucos elementos, o algoritmo é rápido.

Direto, eficiente, sem overhead.

Mas conforme o volume cresce, o comportamento começa a se acumular:

* cada inserção passa a custar mais
* mais elementos precisam ser deslocados
* o tempo total cresce de forma agressiva

Nada disso é surpresa — mas ver acontecendo é diferente.

---

## Gráfico

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CIH/graphic - insertion sort.svg"
       alt="Gráfico Insertion Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Insertion Sort — crescimento acelerado do tempo 
  </p>
</div>

O gráfico deixa isso bem claro.

O crescimento começa controlado, mas rapidamente foge de escala.

É o $n^2$ aparecendo sem suavização.

---

## Um detalhe que chama atenção

O custo do algoritmo não está distribuído de forma uniforme.

Ele se acumula nas inserções.

Quanto mais o *array* cresce, mais caro fica manter a ordenação incremental.

E isso cria um efeito cascata que domina o tempo total.

---

## Limitações

A medição aqui não tenta ser rigorosa ao extremo:

* uma execução por cenário
* dados gerados de forma simples
* sem análise estatística aprofundada

Não é benchmark formal.

Mas também não precisa ser pra mostrar o comportamento.

---

## Por que esse projeto existe

Esse projeto não é sobre o algoritmo em si.

É sobre observar o limite dele.

Porque enquanto o *Insertion Sort* funciona muito bem em cenários pequenos ou parcialmente ordenados, ele tem um ponto claro onde deixa de ser viável.

---

## Fechamento

*Insertion Sort* é simples — e essa simplicidade é exatamente o que o torna útil em certos contextos.

Mas ela também impõe um limite.

Quando você mede, esse limite deixa de ser teórico e vira algo concreto.

E isso muda completamente a forma como você enxerga o algoritmo.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Insertion-Sort).

---
