---
layout: post
title: "Insertion Sort e o que acontece quando você mede"
date: 2026-03-30
categories: portfolio
mathjax: false
tags: [C, Algorithms]
image: /assets/images/insertion-sort.png
github: https://github.com/natamleao/Insertion-Sort
excerpt: "Implementação de Insertion Sort em C com medição de tempo para observar o comportamento na prática."
---

## Ideia

Insertion Sort é um clássico do ensino de algoritmos.

Mas o interessante não é só implementar.

> o interessante é ver como ele se comporta quando você mede de verdade

---

## O que foi feito

Implementei em C:

- uma estrutura de array dinâmica  
- inserção de valores e impressão do array  
- Insertion Sort completo  
- um módulo de medição de tempo usando `clock()`  

O objetivo foi sair do “funciona” e ir pro “quanto custa em tempo real”.

---

## Estrutura

O array é encapsulado na estrutura:

```c
struct _structureArray{
    float *data;
    int size;
    int capacity;
};
````

* `data` → armazena os elementos
* `size` → quantidade de elementos válidos
* `capacity` → capacidade máxima

Nada complexo, mas suficiente para testar o algoritmo com flexibilidade.

---

## Insertion Sort

O algoritmo percorre o array e insere cada elemento na posição correta da parte já ordenada.

* melhor caso → array quase ordenado → `O(n)`
* caso médio → `O(n²)`
* pior caso → array inversamente ordenado → `O(n²)`

---

## Medição

Usei `clock()` do C padrão:

```c
double executionTime = calculateTimeExecutionTime(insertionSorte, structure);
calculateTimePrintExecutionTime(executionTime);
```

Isso permite observar o tempo real de execução, especialmente em arrays grandes.

---

## Um detalhe importante

Medir muda totalmente a percepção do algoritmo.

Você pode saber a complexidade teórica, mas só ao rodar com centenas de milhares de elementos você percebe:

* tempo real gasto
* custo de acesso à memória
* impacto do crescimento quadrático

---

## Limitações

* medição baseada em uma execução
* geração de dados aleatórios simples
* alto uso de memória para arrays grandes

Não compromete o aprendizado, mas é bom ter em mente.

---

## Por que esse projeto

A ideia aqui foi simples:

* implementar um algoritmo clássico
* encapsular em uma estrutura dinâmica
* observar o comportamento real na prática

---

## Código

O projeto completo está disponível [aqui](https://github.com/natamleao/Insertion-Sort).

---
