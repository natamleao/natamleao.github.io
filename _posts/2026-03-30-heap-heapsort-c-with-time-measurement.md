---
layout: post
title: "Heap e HeapSort em C com Medição de Tempo"
date: 2026-03-30
categories: portfolio
mathjax: false
tags: [C, Data Structures, Heap]
image: /assets/images/umbrellan.png
github: https://github.com/natamleao/Heap-HeapSort
excerpt: "Implementação de Max-Heap e HeapSort em C com medição de tempo de execução utilizando clock_gettime."
---

![C](https://img.shields.io/badge/language-C-blue)
![C11](https://img.shields.io/badge/standard-C11-orange)
![Makefile](https://img.shields.io/badge/build-Makefile-green)
![Heap](https://img.shields.io/badge/data_structure-heap-yellow)
![HeapSort](https://img.shields.io/badge/algorithm-heapsort-lightgrey)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## Visão geral

Este projeto implementa uma **Heap (Max-Heap)** em C (C11), juntamente com o algoritmo de ordenação **HeapSort**.

Também inclui um módulo para **medição de tempo de execução** baseado em `clock_gettime`, permitindo observar o comportamento do algoritmo na prática.

---

## Funcionalidades

- Criação de heap a partir de um array  
- Inserção de elementos  
- Remoção do maior elemento  
- Construção de heap (heapify)  
- Ordenação com HeapSort  
- Impressão da estrutura  
- Medição de tempo de execução  
- Liberação de memória  

---

## Estrutura da Heap

A heap é representada como um array:

```

Índice:   0    1    2    3    4    5
Valor:   [90, 70, 50, 30, 20, 10]

```

Relações entre os índices:

```

pai(i) = (i - 1) / 2
esq(i) = 2*i + 1
dir(i) = 2*i + 2

````

---

## Estrutura principal

```c
struct _structureHeap{
    float *_data;
    int _size;
    int _virtualSize;
    int _capacity;
};
````

* `_data`: array que armazena os elementos
* `_size`: número de elementos válidos
* `_virtualSize`: usado no HeapSort para controlar a parte ativa
* `_capacity`: capacidade máxima

---

## HeapSort

```c
void HeapSort(StructureHeap *heap);
```

Etapas:

1. Construção da heap
2. Troca da raiz com o último elemento
3. Redução do tamanho virtual
4. Reorganização com HeapifyDown

Complexidade:

* Tempo: `O(n log n)`
* Espaço: `O(1)`

---

## Medição de tempo

O tempo de execução é medido com `clock_gettime` usando `CLOCK_MONOTONIC`.

```c
double executionTime = calculateTime(HeapSort, heap);
calculateTimePrintTime(executionTime);
```

Exemplo de saída:

```
Tempo de execução: 0 H : 0 M : 0 S : 12 ms
```

---

## Estrutura do projeto

```text
Heap-HeapSort/
│
├── app/
├── src/
├── include/
├── build/
├── bin/
├── lib/
│
├── Makefile
├── README.md
└── LICENSE
```

---

## Execução

```bash
git clone https://github.com/natamleao/Heap-HeapSort.git
cd Heap-HeapSort
make
make run
```

Limpeza:

```bash
make clean
make cleanapp
```

**Requisitos:** GCC ou Clang e GNU Make.

---

## Observações

* A implementação utiliza Max-Heap
* O HeapSort é realizado in-place
* A medição de tempo é baseada em uma única execução
* O tamanho dos dados de teste pode exigir alto uso de memória

---

## Conclusão

O projeto implementa uma estrutura clássica e um algoritmo de ordenação eficiente, além de permitir observar seu desempenho em execução real.

---

[Veja o projeto no GitHub](https://github.com/natamleao/Heap-HeapSort)

---
