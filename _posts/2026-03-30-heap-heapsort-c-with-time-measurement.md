---
layout: post
title: "Heap, Heap Sort e o que acontece quando você mede"
date: 2026-03-30
categories: portfolio
mathjax: false
tags: [C, Data Structures]
image: /assets/images/umbrellan.png
github: https://github.com/natamleao/Heap-HeapSort
excerpt: "Implementação de heap e Heap Sort em C com medição de tempo para observar o comportamento na prática."
---

## Ideia

*Heap* e *Heap Sort* são clássicos.

Mas implementar não é o mais interessante.

> o interessante é ver como isso se comporta quando você mede de verdade

---

## O que foi feito

Implementei em C:

- uma *Max-Heap* baseada em *array*  
- operações essenciais para o *Heap Sort* (*heapify* e construção da *heap*)  
- *Heap Sort* *in-place*  
- um módulo de medição de tempo com `clock_gettime`  

A ideia foi sair do “funciona” e ir pro “quanto custa”.

---

## Estrutura

A *heap* é representada como um *array*, usando as relações clássicas:

- pai → `(i - 1) / 2`  
- filho esquerdo → `2*i + 1`  
- filho direito → `2*i + 2`  

Nada fora do padrão — o foco aqui não foi reinventar a estrutura.

---

## Heap Sort

O algoritmo segue o fluxo esperado:

1. construir a *heap*  
2. trocar a raiz com o último elemento  
3. reduzir a parte ativa  
4. reorganizar com *heapify*  

Aqui implementei apenas o necessário para o processo de ordenação, sem operações completas de manipulação como inserção ou remoção genérica.

---

## Medição

Usei `clock_gettime` com `CLOCK_MONOTONIC`.

Isso evita interferência de ajustes no relógio do sistema e dá uma medição mais confiável.

No código:

```c
double executionTime = executionTimeCalculate(heapSort, heap);
executionTimePrint(executionTime);
````

---

## Um detalhe importante

Medir muda a forma como você olha o algoritmo.

Uma coisa é saber que *Heap Sort* é `O(n log n)`.

Outra é:

* rodar com milhões de elementos
* ver o tempo real
* perceber custo de memória e alocação

---

## Limitações

* medição baseada em uma execução
* geração de dados aleatórios simples
* uso de memória elevado para testes grandes

Nada crítico — mas importante deixar claro.

---

## Por que esse projeto

A ideia aqui foi simples:

* implementei uma estrutura clássica
* apliquei um algoritmo conhecido
* observei o comportamento na prática

---

## Código

O projeto completo está disponível [aqui](https://github.com/natamleao/Heap-HeapSort).

---
