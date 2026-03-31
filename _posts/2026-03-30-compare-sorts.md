---
layout: post
title: "Comparando HeapSort e Insertion Sort: tempo real"
date: 2026-03-30
categories: portfolio
mathjax: true
tags: [C, Algorithms, Data Structures]
image: "/assets/images/heap-vs-insertion.png"
github: "https://github.com/natamleao/Compare-Sorts"
excerpt: "Comparação prática entre HeapSort e Insertion Sort em C com medição de tempo, mostrando o custo real de cada algoritmo."
---

## Ideia

Ver **HeapSort e Insertion Sort** lado a lado é um contraste bem interessante.

> implementar é fácil. medir e comparar mostra a diferença de verdade.

---

## O que fiz

Criei um programa em C que:

* Inicializa **mesmos dados** para os dois algoritmos
* HeapSort com **Max-Heap**
* Insertion Sort com **_array_ dinâmico**
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

### _Array_ para Insertion Sort

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

Isso permite comparar **tempo real para o mesmo _array_**.

---

## Gráficos de comparação

* **Gráfico 1:** HeapSort — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/HeapSort — tempo de execução vs tamanho da entrada.svg"
       alt="Gráfico HeapSort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    HeapSort — crescimento do tempo de execução (escala log)
  </p>
</div>

* **Gráfico 2:** InsertionSort — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/InsertionSort — crescimento do tempo de execução.svg"
       alt="Gráfico InsertionSort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    InsertionSort — crescimento acelerado do tempo (escala log)
  </p>
</div>

* **Gráfico 3:** HeapSort vs InsertionSort — comparação de tempo

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/HeapSort vs InsertionSort — comparação de tempo.svg"
       alt="Comparação HeapSort vs InsertionSort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    HeapSort vs InsertionSort — diferença de crescimento (escala log)
  </p>
</div>

> Tentei escalar o experimento para 50 milhões de elementos, depois de horas rodando, ficou claro: o algoritmo simplesmente deixa de ser viável.
> Isso já era sabido, dado que no médio/pior caso ele é $O(n²)$, ou seja, $(5 \times 10^7)^2 = 2.5 \times 10^{15}$ operações.
> Estimando poucos nanossegundos por operação, isso levaria meses — possivelmente anos — para terminar.

---

## Observações pessoais

Medir lado a lado foi revelador:

* HeapSort domina com _arrays_ grandes
* Insertion Sort “explode” rapidamente conforme o tamanho cresce
* Mesmo conhecendo a complexidade, **ver os números reais é incrível**
* Dá pra perceber o custo da memória, cache, e operações de movimentação

> Aprendi que teoria + prática é outra história.

---

## Limitações

* Medição baseada em uma execução
* Dados gerados aleatoriamente simples
* _arrays_ grandes exigem muita memória

Ainda assim, suficiente para comparar de verdade os algoritmos.

---

## Por que esse projeto

Quis criar algo que fosse mais que código funcional:

* Coloquei dois algoritmos clássicos lado a lado
* Medições reais mostram limites práticos
* Experiência direta ajuda a **entender comportamento real** de cada algoritmo

---

## Código

O projeto completo está disponível [aqui](https://github.com/natamleao/Compare-Sorts).

---
