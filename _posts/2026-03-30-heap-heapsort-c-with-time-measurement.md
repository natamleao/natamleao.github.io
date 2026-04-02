---
layout: post
title: "Heap, Heap Sort e o que acontece quando você mede"
date: 2026-03-30
categories: portfolio
mathjax: true
tags: [C, Data Structures]
image: /assets/images/umbrellan.png
github: https://github.com/natamleao/Heap-HeapSort
excerpt: "Implementação de heap e Heap Sort em C com medição de tempo para observar o comportamento na prática."
---

## O ponto de partida

*Heap* e *Heap Sort* não têm mistério. São estruturas e algoritmos bem estabelecidos, bem documentados e já explorados até o limite.

Então a motivação aqui não foi “entender como funciona”.

Foi outra coisa:

> sair do nível teórico e olhar o comportamento quando você mede de fato

---

## Implementar é o básico

A implementação seguiu o caminho padrão:

* *max-heap* baseada em *array*
* relações clássicas entre pai e filhos
* construção da *heap*
* *heapify*
* ordenação *in-place*

Nada fora do esperado.

E isso é proposital — quando a base é conhecida, fica mais fácil observar o que realmente interessa depois.

---

## Onde começa a ficar interessante

A diferença aqui foi adicionar medição de tempo de execução usando `clock_gettime`.

Não como detalhe, mas como parte central do projeto.

Porque até então, *Heap Sort* é só mais um algoritmo com complexidade $O(n \log n)$.

Mas isso, sozinho, não diz muita coisa na prática.

---

## O que muda quando você mede

Quando você roda o algoritmo com volumes maiores de dados, algumas coisas começam a ficar mais concretas:

* o crescimento do tempo deixa de ser abstrato
* o custo de reorganizar a *heap* aparece com mais clareza
* o impacto de trabalhar *in-place* fica evidente

Nada disso contradiz a teoria — mas também não é algo que você “sente” só olhando pra notação assintótica.

Tem uma diferença grande entre saber e observar.

---

## Gráfico: crescimento do tempo

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/Gráfico - Heap Sort.svg"
       alt="Gráfico Heap Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Heap Sort — crescimento do tempo de execução (escala log)
  </p>
</div>

O comportamento é bem estável.

O tempo cresce, claro, mas de forma controlada — sem aquele salto abrupto que aparece em algoritmos quadráticos.

---

## Um detalhe que chama atenção

Uma coisa que fica clara é como o custo está concentrado.

A construção da *heap* é relativamente rápida.
Mas o processo de extração + *heapify* repetido é onde o algoritmo realmente “paga o preço”.

É ali que o $\log n$ aparece repetidamente, acumulando custo ao longo da execução.

---

## Limitações

A medição aqui não tenta ser rigorosa ao extremo:

* uma execução por cenário
* dados gerados de forma simples
* sem análise estatística aprofundada

Não é benchmark científico.

Mas também não era essa a intenção.

---

## Por que esse projeto existe

Esse projeto não é sobre reinventar *Heap Sort*.

É sobre dar um passo além do “funciona” e entrar no “como se comporta”.

Porque em algum momento, só saber a teoria começa a ficar pouco.

---

## Fechamento

No fim, a estrutura e o algoritmo são os mesmos de sempre.

O que muda é a forma de olhar.

Quando você mede, a complexidade deixa de ser só uma ideia e vira algo observável — quase palpável.

E isso, por mais simples que pareça, muda bastante a forma como você enxerga algoritmos clássicos.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Heap-HeapSort).

---
