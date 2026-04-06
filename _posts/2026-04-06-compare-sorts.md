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

## Por que comparar seis algoritmos clássicos?

Algoritmos como *Bubble Sort*, *Insertion Sort*, *Selection Sort*, *Quick Sort*, *Merge Sort* e sua versão otimizada do *Bubble Sort* são clássicos da ciência da computação.

Cada um tem características próprias:

* Simplicidade vs complexidade
* Crescimento quadrático vs logarítmico
* Efeito real na prática, dependendo do tamanho do conjunto de dados

A ideia aqui foi colocar **todos sob as mesmas condições** e medir os tempos reais de execução.

---

## Como montei o experimento

Nada sofisticado, mas consistente:

* Cada algoritmo recebe **os mesmos dados aleatórios**
* Estruturas separadas para não interferir entre implementações
* Medição com `clock_gettime` usando `CLOCK_MONOTONIC`
* Conjunto de dados escalonado, indo de 1.000 até 1.000.000 de elementos

O foco é mostrar **tempo real de execução**, não apenas complexidade teórica.

---

## Estruturas utilizadas

Cada algoritmo roda sobre sua própria estrutura:

* *Bubble Sort* e *Optimized Bubble Sort* usam array dinâmico
* *Insertion Sort* usa array dinâmico
* *Selection Sort* idem
* *Quick Sort* e *Merge Sort* operam sobre arrays através de funções recursivas auxiliares

Isso garante medições justas.

---

## Medição de tempo

O tempo é calculado assim:

```c
double elapsed(struct timespec a, struct timespec b){
    return (b.tv_sec - a.tv_sec) * 1e9 + (b.tv_nsec - a.tv_nsec);
}

double executionTimeCalculate(void (*function)(void *), void *data){
    struct timespec t1, t2;
    clock_gettime(CLOCK_MONOTONIC, &t1);
    function(data);
    clock_gettime(CLOCK_MONOTONIC, &t2);
    
    return elapsed(t1, t2); // retorna em segundos (double)
}
````

E exibido em formato legível:

```c
void executionTimePrint(double executionTime){
    printf("Tempo de execução: %.6f ms\n", executionTime / 1e6);
}
```

---

## Gráficos de comparação

> Aqui você deve adicionar os gráficos de tempo para cada algoritmo, assim como o gráfico geral comparativo.

* **Gráfico 1:** Bubble Sort — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/bubble-sort.svg"
       alt="Bubble Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

* **Gráfico 2:** Optimized Bubble Sort — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/optimized-bubble-sort.svg"
       alt="Optimized Bubble Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

* **Gráfico 3:** Insertion Sort — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/insertion-sort.svg"
       alt="Insertion Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

* **Gráfico 4:** Selection Sort — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/selection-sort.svg"
       alt="Selection Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

* **Gráfico 5:** Merge Sort — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/merge-sort.svg"
       alt="Merge Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

* **Gráfico 6:** Quick Sort — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/quick-sort.svg"
       alt="Quick Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

* **Gráfico 7:** Comparação direta — todos os algoritmos

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/comparison-all-sorts.svg"
       alt="Comparação geral"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

---

## Observações

* Algoritmos quadráticos (*Bubble*, *Insertion*, *Selection*) crescem rápido demais com a escala
* *Merge Sort* e *Quick Sort* mantêm crescimento estável
* Optimized Bubble melhora, mas ainda é inviável em grandes conjuntos
* Colocando tudo lado a lado, fica evidente o efeito real da complexidade

---

## Conclusão

Este projeto deixa explícita a diferença entre **O(n²)** e **O(n log n)** no mundo real.

Medir é diferente de só calcular complexidade.

A escolha do algoritmo impacta diretamente na prática — e não só na teoria.

--- 

## Código 

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Compare-Sorts). 

---
