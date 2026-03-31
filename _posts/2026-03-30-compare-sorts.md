---
layout: post
title: "Comparando HeapSort e Insertion Sort: tempo real"
date: 2026-03-30
categories: portfolio
mathjax: true
tags: [C, Algorithms, Data Structures]
image: "/assets/images/heap-vs-insertion.png"
github: "https://github.com/natamleao/Heap-HeapSort"
excerpt: "Comparação prática entre HeapSort e Insertion Sort em C com medição de tempo, mostrando o custo real de cada algoritmo."
---

## Ideia

Ver **HeapSort e Insertion Sort** lado a lado é um contraste bem interessante.

> Implementar é fácil. Medir e comparar é quando a realidade aparece.

---

## O que fiz

Criei um programa em C que:

* Inicializa **mesmos dados** para os dois algoritmos
* HeapSort com **Max-Heap**
* Insertion Sort com **array dinâmico**
* Medição de tempo precisa com `clock_gettime` e `CLOCK_MONOTONIC`
* Compara **tempo de execução real**

Queria sair do “funciona” e ir direto para “quanto custa na prática”.

---

## Estruturas usadas

### Heap para HeapSort

```c
struct _structureHeap{
    float *_data;
    int _size;
    int _virtualSize;
    int _capacity;
};
```

### Array para Insertion Sort

```c
struct _structureArray{
    float *_data;
    int _size;
    int _capacity;
};
```

Cada estrutura encapsula os dados e mantém o algoritmo isolado para medir com precisão.

---

## Algoritmos

### HeapSort

1. Construção da heap
2. Troca da raiz com o último elemento
3. Redução do tamanho ativo
4. HeapifyDown

*Complexidade:* $O(nlog\,n)$ _in-place_, escalável para milhões de elementos.

---

### Insertion Sort

Percorre o _array_, inserindo cada elemento na posição correta da parte já ordenada.

*Complexidade:*

* Melhor caso $\to O(n)$
* Médio/pior caso $\to O(n²)$

---

## Medição de tempo

Usei `clock_gettime` com `CLOCK_MONOTONIC` para capturar **tempo real de execução**, evitando interferência do sistema:

```c
double executionTimeHeapSort = executionTimeCalculate(heapSortWrapper, arrayHeapSort);
executionTimePrint(executionTimeHeapSort);

double executionTimeInsertionSort = executionTimeCalculate(insertionSortWrapper, arrayInsertionSort);
executionTimePrint(executionTimeInsertionSort);
```

Isso permite comparar **tempo real para o mesmo array**.

---

## Gráficos de comparação

* **Gráfico 1:** HeapSort (tempo real)

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/Tempo - HeapSort.svg"
       alt="Neurônio artificial"
       style="display: block; margin: 0 auto; max-width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Tempo real - HeapSort
  </p>
</div>

* **Gráfico 2:** Insertion Sort (tempo real)

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/Tempo - InsertionSort.svg"
       alt="Neurônio artificial"
       style="display: block; margin: 0 auto; max-width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Tempo real - Insertion Sort
  </p>
</div>

* **Gráfico 3:** HeapSort x Insertion Sort (tempo real)

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/Comparação - HeapSort vs InsertionSort.svg"
       alt="Neurônio artificial"
       style="display: block; margin: 0 auto; max-width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Tempo real - Comparação - HeapSort vs Insertion Sort
  </p>
</div>

> Tentei escalar o experimento para 50 milhões de elementos, depois de horas de execução, ficou evidente: o algoritmo se torna inviável antes mesmo de completar.
> Isso já era sabido, dado que no médio/pior caso ele é $O(n²)$, ou seja, $(50.000.000)² = 2,5x10^{15}$ de operações.

---

## Observações pessoais

Medir lado a lado foi revelador:

* HeapSort domina com _arrays_ grandes
* Insertion Sort “explode” rapidamente conforme o tamanho cresce
* Mesmo conhecendo a complexidade, **ver os números reais é chocante**
* Dá pra perceber o custo da memória, cache, e operações de movimentação

> Aprendi que teoria + prática é outra história.

---

## Limitações

* Medição baseada em uma execução
* Dados gerados aleatoriamente simples
* Arrays grandes exigem muita memória

Ainda assim, suficiente para comparar de verdade os algoritmos.

---

## Por que esse projeto

Quis criar algo que fosse mais que código funcional:

* Coloquei dois algoritmos clássicos lado a lado
* Medições reais mostram limites práticos
* Experiência direta ajuda a **entender comportamento real** de cada algoritmo

---

## Código

O projeto completo está disponível [aqui](https://github.com/natamleao/Heap-HeapSort).

---
