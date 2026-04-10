---
layout: post
title: "Comparando algoritmos de ordenação com diferentes tamanhos de entrada"
date: 2026-04-06
categories: portfolio
mathjax: true
tags: [C, Algorithms, Sorting]
image: "/assets/images/sorts-comparison.png"
github: https://github.com/natamleao/Compare-Sorts
excerpt: "Comparação prática de algoritmos de ordenação em C com benchmark baseado em múltiplas execuções e cópias isoladas dos dados."
---

## A comparação é simples e evidencia a diferença teórica de complexidade

*Bubble Sort*, *Insertion Sort*, *Selection Sort*, *Quick Sort* e *Merge Sort* aparecem em introdução à computação.

Alguns são simples.
Outros são eficientes.
$O(n²)\; \text{vs}\; O(n\log\,n)$.

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

## Estrutura dos dados

Foi utilizada uma estrutura própria:

```c
typedef struct{
    float *_data;
    int _size;
} StructureArray;
````

Ela encapsula:

* dados dinâmicos (`float*`)
* tamanho do *array*

Isso facilita controle de memória e organização do código.

---

## *Benchmark* (o ponto mais importante)

Cada algoritmo não roda apenas uma vez.

O processo é:

1. O *array* original é gerado
2. São criadas **100 cópias independentes**
3. Cada cópia é ordenada separadamente
4. O tempo médio é calculado

Isso evita um problema clássico:

> medir algoritmo sobre *array* já ordenado sem perceber

Trecho simplificado:

```c
double time = benchmarkExecutionTime(bubbleSort, data, size);
executionTimePrint(time);
```

---

## Geração dos dados

Os valores são gerados aleatoriamente no intervalo: ```[-1e6, 1e6]```

E copiados para todos os algoritmos, garantindo:

* mesma distribuição
* mesma dificuldade
* comparação justa

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

## Escalabilidade 

Com entradas pequenas:

* tudo funciona
* diferenças são pequenas

Mas isso não dura.

Quando o tamanho cresce, a complexidade começa a mandar no jogo.

---

## Gráficos de comparação

* **Gráfico 1**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - bubble-sort.svg"
       alt="Bubble Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Bubble Sort — crescimento do tempo
  </p>
</div>

---

* **Gráfico 2**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - optimized-bubble-sort.svg"
       alt="Optimized Bubble Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Optimized Bubble Sort — crescimento do tempo
  </p>
</div>

---

* **Gráfico 3**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - insertion-sort.svg"
       alt="Insertion Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Insertion Sort — crescimento do tempo
  </p>
</div>

---

* **Gráfico 4**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - selection-sort.svg"
       alt="Selection Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Selection Sort — crescimento do tempo
  </p>
</div>

---

* **Gráfico 5**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - merge-sort.svg"
       alt="Merge Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Merge Sort — crescimento do tempo
  </p>
</div>

---

* **Gráfico 6**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - quick-sort.svg"
       alt="Quick Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Quick Sort — crescimento do tempo
  </p>
</div>

---

* **Gráfico 7**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - comparison-all-sorts.svg"
       alt="Comparação geral"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Comparação direta entre todos os algoritmos
  </p>
</div>

---

## Tabela de tempos

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/times-table.png"
       alt="Tabela de tempos"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Tempos médios de execução (ms)
  </p>
</div>

---

## Quando alguns algoritmos deixam de ser opção

Existe um ponto onde não é mais questão de otimizar.

É limite estrutural.

Algoritmos $O(n^2)$:

* crescem rápido demais
* deixam de ser práticos
* viram inviáveis

---

## O que fica evidente

Quando você mede de verdade:

* algoritmos quadráticos colapsam rápido
* otimizações ajudam, mas não resolvem
* *Merge Sort* e *Quick Sort* escalam bem
* a diferença deixa de ser teórica

E principalmente:

> chega um ponto em que o algoritmo deixa de ser lento e passa a ser inútil

---

## Fechamento

Nada aqui é novo.

Mas medir muda tudo.

Quando você coloca teoria contra dados reais:

* complexidade vira comportamento
* comportamento vira decisão

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Compare-Sorts).

---
