---
layout: post
title: "Comparando diferentes algoritmos de ordenação em C"
date: 2026-04-06
categories: portfolio
mathjax: true
tags: [C, Algorithms, Sorting]
image: "/assets/images/sorts-comparison.png"
github: https://github.com/natamleao/Compare-Sorts
excerpt: "Comparação prática de Bubble Sort, Insertion Sort, Optimized Bubble, Selection Sort, Merge Sort e Quick Sort em C com medição de tempo."
---

## A comparação que parece simples — mas muda quando você mede

*Bubble Sort*, *Insertion Sort*, *Selection Sort*, *Quick Sort* e *Merge Sort* aparecem em qualquer introdução à computação.

Alguns são simples.
Outros são eficientes.
$O(n²)\; \text{vs}\; O(n \log n)$.

Beleza. Isso todo mundo já viu.

Mas essa comparação normalmente para na teoria.

Aqui a ideia foi ir além:

> colocar todos sob as mesmas condições e observar o comportamento real

---

## Como montei o experimento

Nada exagerado — mas com controle suficiente pra não distorcer o resultado:

* todos os algoritmos recebem **os mesmos dados**
* cada execução é isolada
* medição com `clock_gettime` usando `CLOCK_MONOTONIC`
* foco direto em tempo de execução

Não é benchmark acadêmico — mas também não é chute.

---

## Estruturas

Cada algoritmo roda de forma independente:

* *Bubble Sort* e *Optimized Bubble Sort* com array dinâmico
* *Insertion Sort* com array dinâmico
* *Selection Sort* com array dinâmico
* *Quick Sort* e *Merge Sort* com funções recursivas sobre arrays

Isso evita interferência e mantém a comparação justa.

---

## Ambiente de execução

Os testes foram executados no meu notebook:

* CPU: AMD Ryzen 7 5825U (8 cores / 16 threads)
* RAM: 7.2 GiB
* Sistema: Debian GNU/Linux 12 (Bookworm)
* Arquitetura: x86-64
* Armazenamento: SSD
* Compilador: GCC
* Flags: `-O2 -Wall -Werror`

Tempo de execução depende diretamente do ambiente — não é absoluto.

---

## O que acontece quando você escala

Com entradas pequenas, todos convivem bem.

Os algoritmos quadráticos até parecem aceitáveis.

Mas isso não dura.

Conforme o tamanho cresce, a diferença deixa de ser detalhe e vira estrutura.

---

## Gráficos de comparação

* **Gráfico 1:** *Bubble Sort* — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - bubble-sort.svg"
       alt="Bubble Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

---

* **Gráfico 2:** *Optimized Bubble Sort* — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - optimized-bubble-sort.svg"
       alt="Optimized Bubble Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

---

* **Gráfico 3:** *Insertion Sort* — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - insertion-sort.svg"
       alt="Insertion Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

---

* **Gráfico 4:** *Selection Sort* — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - selection-sort.svg"
       alt="Selection Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

---

* **Gráfico 5:** *Merge Sort* — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - merge-sort.svg"
       alt="Merge Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

---

* **Gráfico 6:** *Quick Sort* — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - quick-sort.svg"
       alt="Quick Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

---

* **Gráfico 7:** Comparação direta — todos os algoritmos

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - comparison-all-sorts.svg"
       alt="Comparação geral"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

---

## Tabela de tempos de execução

A tabela abaixo apresenta os tempos de execução (em milissegundos) para cada algoritmo:

| N (elementos) | Bubble (ms) | Opt. Bubble (ms) | Insertion (ms) | Selection (ms) | Merge (ms) | Quick (ms) |
|--------------|-------------|------------------|----------------|----------------|------------|------------|
|              |             |                  |                |                |            |            |
|              |             |                  |                |                |            |            |
|              |             |                  |                |                |            |            |
|              |             |                  |                |                |            |            |
|              |             |                  |                |                |            |            |

> *Obs.: valores ausentes indicam execuções inviáveis ou não realizadas devido ao alto custo computacional.*

---

## O ponto onde alguns algoritmos deixam de ser opção

Em determinado momento, alguns algoritmos simplesmente deixam de ser utilizáveis.

Não é questão de otimização.

É limite estrutural.

Algoritmos $O(n²)$ começam a crescer rápido demais.

E aí não importa quão bem você implementou — eles não escalam.

---

## O que ficou evidente

Algumas coisas ficam muito claras quando você mede:

* algoritmos quadráticos degradam rápido
* otimizações ajudam, mas não salvam
* *Merge Sort* e *Quick Sort* mantêm crescimento controlado
* a diferença não é teórica — é prática

E principalmente:

> chega um ponto em que o algoritmo deixa de ser lento e passa a ser inviável

---

## Fechamento

Esse projeto não tenta provar nada novo.

Só coloca vários algoritmos clássicos no mesmo cenário e mede o comportamento real.

E quando você faz isso, complexidade deixa de ser notação.

Vira decisão.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Compare-Sorts).

---