---
layout: post
title: "Comparando Heap Sort e Insertion Sort: tempo real"
date: 2026-03-30
categories: portfolio
mathjax: true
tags: [C, Algorithms, Data Structures]
image: "/assets/images/heap-vs-insertion.png"
github: "https://github.com/natamleao/Compare-Sorts"
excerpt: "Comparação prática entre Heap Sort e Insertion Sort em C com medição de tempo, mostrando o custo real de cada algoritmo."
---

## Ideia

Ver **Heap Sort e Insertion Sort** lado a lado é um contraste bem interessante.

> implementar é fácil. medir e comparar mostra a diferença de verdade.

---

## O que fiz

Criei um programa em C que:

* Inicializa **mesmos dados** para os dois algoritmos  
* *Heap Sort* com **Max-Heap**  
* *Insertion Sort* com **_array_ dinâmico**  
* Medição de tempo precisa com `clock_gettime` e `CLOCK_MONOTONIC`  
* Compara **tempo de execução real**  

Queria sair do “funciona” e ir direto para “quanto custa na prática”.

---

## Estruturas usadas

### Heap para *Heap Sort*

```c
struct _structureHeap{
    float *_data;
    int _size, _virtualSize;
};
````

### *Array* para *Insertion Sort*

```c
struct _structureArray{
    float *_data;
    int _size;
};
```

Cada estrutura encapsula os dados e mantém o algoritmo isolado para medir com precisão.

---

## Algoritmos

### *Heap Sort*

1. Construção da *heap*
2. Troca da raiz com o último elemento
3. Redução do tamanho ativo
4. *HeapifyDown*

**Complexidade:** $O(n \log n)$ *in-place*, escalável para milhões de elementos.

---

### *Insertion Sort*

Percorre o *array*, inserindo cada elemento na posição correta da parte já ordenada.

**Complexidade:**

* Melhor caso $\to O(n)$
* Médio/pior caso $\to O(n²)$

---

## Medição de tempo

Usei `clock_gettime` com `CLOCK_MONOTONIC` para capturar **tempo real de execução**, evitando interferência do sistema:

```c
double executionTimeHeapSort = executionTimeCalculate(heapSortWrapper, arrayHeap);
executionTimePrint(executionTimeHeapSort);

double executionTimeInsertionSort = executionTimeCalculate(insertionSortWrapper, arrayInsertion);
executionTimePrint(executionTimeInsertionSort);
```

Isso permite comparar **tempo real para o mesmo *array***.

---

## Ambiente de execução

Os testes foram executados no meu notebook:

* CPU: AMD Ryzen 7 5825U (8 cores / 16 threads)
* RAM: 7.2 GiB
* Sistema: Debian GNU/Linux 12 (Bookworm)
* Arquitetura: x86-64
* Armazenamento: SSD
* Compilador: GCC
* Flags de compilação: `-O2 -Wall -Werror`

Isso importa porque tempo de execução não é absoluto — depende diretamente do *hardware* e da forma como o código é compilado.

A ideia aqui não é obter números universais, mas observar o comportamento real dos algoritmos no mesmo ambiente.

---

## Gráficos de comparação

* **Gráfico 1:** *Heap Sort* — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/Gráfico - Heap Sort.svg"
       alt="Gráfico Heap Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Heap Sort — crescimento do tempo de execução (escala log)
  </p>
</div>

* **Gráfico 2:** *Insertion Sort* — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/Gráfico - Insertion Sort.svg"
       alt="Gráfico Insertion Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Insertion Sort — crescimento acelerado do tempo (escala log)
  </p>
</div>

* **Gráfico 3:** *Heap Sort* vs *Insertion Sort* — comparação de tempo

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/Gráfico - Heap Sort vs Insertion Sort.svg"
       alt="Comparação Heap Sort vs Insertion Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Heap Sort vs Insertion Sort — diferença de crescimento (escala log)
  </p>
</div>

> Tentei escalar o experimento para 50 milhões de elementos. Depois de horas rodando, ficou claro: o algoritmo simplesmente deixa de ser viável.
> Isso já era esperado, já que no médio/pior caso ele é $O(n²)$, ou seja, $(5 \times 10^7)^2 = 2.5 \times 10^{15}$ operações.
> Mesmo assumindo poucos nanossegundos por operação, isso facilmente escala para meses — possivelmente anos.

---

## Observações pessoais

Medir lado a lado foi revelador:

* *Heap Sort* domina com *arrays* grandes
* *Insertion Sort* “explode” rapidamente conforme o tamanho cresce
* Mesmo conhecendo a complexidade, **ver os números reais é outro nível**
* Dá pra perceber custo de memória, cache e movimentação de dados

> Teoria te dá o mapa. Medição te mostra o terreno de verdade.

---

## Limitações

* Medição baseada em uma execução
* Dados gerados aleatoriamente simples
* *arrays* grandes exigem muita memória

Ainda assim, suficiente para comparar de verdade os algoritmos.

---

## Por que esse projeto

Quis criar algo que fosse mais que código funcional:

* coloquei dois algoritmos clássicos lado a lado
* medi o comportamento real
* vi na prática onde cada um quebra

---

## Código

O projeto completo está disponível [aqui](https://github.com/natamleao/Compare-Sorts).

---
