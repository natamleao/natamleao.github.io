---
layout: post
title: "Comparando diferentes algoritmos de ordenação com diferentes tamanhos de entradas"
date: 2026-04-06
categories: portfolio
mathjax: true
tags: [C, Algorithms, Sorting]
image: "/assets/images/sorts-comparison.png"
github: https://github.com/natamleao/Compare-Sorts
excerpt: "Comparação prática de Bubble Sort, Insertion Sort, Optimized Bubble, Selection Sort, Merge Sort e Quick Sort em C com medição de tempo."
---

## A comparação é simples e evidencia a diferença teórica de complexidade

*Bubble Sort*, *Insertion Sort*, *Selection Sort*, *Quick Sort* e *Merge Sort* aparecem em introdução à computação.

Alguns são simples.
Outros são eficientes.
$O(n²)\; \text{vs}\; O(n \log n)$.

Beleza. Isso quase todo mundo já viu.

Mas essa comparação normalmente para na teoria.

Aqui a ideia foi ir à prática:

> colocar todos sob as mesmas condições e observar o comportamento e tempo reais

---

## Como montei o experimento

Nada muito "acadêmico" — mas com controle suficiente pra não distorcer o resultado:

* todos os algoritmos recebem **os mesmos dados**
* cada execução é isolada
* medição com `clock_gettime` usando `CLOCK_MONOTONIC`
* foco direto em tempo de execução

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

Isso é necessário deixar claro, o tempo depende e vária de máquina para máquina.

---

## O que acontece quando se escala

Com entradas pequenas, todos convivem bem.

Os algoritmos quadráticos até parecem aceitáveis.

Mas isso não dura.

Conforme o tamanho cresce, a diferença deixa de ser detalhe e vira estrutura.

---

## Gráficos de comparação

* **Gráfico 1**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - bubble-sort.svg"
       alt="Bubble Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Bubble Sort — crescimento do tempo de execução
  </p>
</div>

---

* **Gráfico 2**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - optimized-bubble-sort.svg"
       alt="Optimized Bubble Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Optimized Bubble Sort — crescimento do tempo de execução
  </p>
</div>

---

* **Gráfico 3** 

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - insertion-sort.svg"
       alt="Insertion Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Insertion Sort — crescimento do tempo de execução
  </p>
</div>

---

* **Gráfico 4**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - selection-sort.svg"
       alt="Selection Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Selection Sort — crescimento do tempo de execução
  </p>
</div>

---

* **Gráfico 5** 

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - merge-sort.svg"
       alt="Merge Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Merge Sort — crescimento do tempo de execução
  </p>
</div>

---

* **Gráfico 6** 

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - quick-sort.svg"
       alt="Quick Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Quick Sort — crescimento do tempo de execução
  </p>
</div>

---

* **Gráfico 7** 

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - comparison-all-sorts.svg"
       alt="Comparação geral"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Comparação direta — todos os algoritmos
  </p>
</div>

---

## Tabela de tempos de execução

A tabela abaixo apresenta os tempos de execução (em milissegundos) para cada algoritmo:

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/times-table.png"
       alt="Selection Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Tabela - tempos de execução (ms)
  </p>
</div>

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
* otimizações ajudam, mas não salvam, como no caso do *Bubble Sort* otimizado
* *Merge Sort* e *Quick Sort* mantêm crescimento controlado
* a diferença não é teórica — é prática

E principalmente:

> chega um ponto em que o algoritmo deixa de ser lento e passa a ser inviável

---

## Fechamento

Esse projeto não tenta provar nada novo.

Só coloca vários algoritmos clássicos no mesmo cenário e mede o comportamento real.

E quando você faz isso, coloca a complexidade em tempo real.

Vira decisão.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Compare-Sorts).

---
