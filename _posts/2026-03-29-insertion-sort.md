---
layout: post
title: "Insertion Sort e o que acontece quando você mede"
date: 2026-03-30
categories: portfolio
mathjax: true
tags: [C, Algorithms]
image: /assets/images/insertion-sort.png
github: https://github.com/natamleao/Insertion-Sort
excerpt: "Implementação de Insertion Sort em C com medição de tempo para observar o comportamento na prática."
---

## De onde veio a ideia

*Insertion Sort* é um daqueles algoritmos que todo mundo vê cedo.

Simples, direto, fácil de implementar.

Mas quase sempre ele fica só no nível conceitual: você aprende como funciona, entende a complexidade e segue em frente.

Aqui a ideia foi parar um pouco nisso e fazer algo mais concreto:

> medir o comportamento real do algoritmo

---

## O que foi feito

Implementei em C:

* uma estrutura de *array* dinâmica
* o algoritmo completo de *Insertion Sort*
* um módulo de medição de tempo com `clock_gettime`

A proposta foi manter tudo simples e focar no comportamento do algoritmo, não na infraestrutura.

---

## O algoritmo

O funcionamento é direto:

* percorre o *array*
* pega o elemento atual
* insere na posição correta da parte já ordenada

Em termos de complexidade:

* melhor caso $\to O(n)$
* médio/pior caso $\to O(n²)$

Nada fora do esperado.

---

## Medindo na prática

A medição usa `CLOCK_MONOTONIC`, evitando interferência externa e mantendo consistência nos resultados.

Isso permite observar o tempo de execução conforme o tamanho do *array* cresce.

E é aí que o comportamento teórico começa a aparecer de forma concreta.

---

## Gráfico: crescimento do tempo

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/Gráfico - Insertion Sort.svg"
       alt="Gráfico Insertion Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Insertion Sort — crescimento do tempo de execução (escala log)
  </p>
</div>

O gráfico deixa claro o padrão:

o crescimento começa controlado, mas rapidamente acelera.

É o comportamento quadrático se acumulando conforme o tamanho aumenta.

---

## O que isso mostra

Enquanto o *array* é pequeno, o algoritmo funciona bem.

Mas à medida que cresce, cada inserção passa a custar mais — porque envolve deslocar uma parte maior dos elementos.

Esse custo se soma repetidamente, e o resultado aparece no tempo final.

---

## Limitações

* medição baseada em uma execução
* dados gerados de forma simples
* uso de memória crescente com o tamanho do *array*

Nada que invalide o experimento, mas importante considerar.

---

## Por que explorar isso

A ideia aqui foi simples:

> sair da complexidade teórica e observar o comportamento real

Sem mudar o algoritmo, sem otimizações específicas — apenas medir.

---

## Fechamento

*Insertion Sort* continua sendo um algoritmo simples e útil em cenários específicos.

Mas quando o problema cresce, o custo aparece rápido.

E medir isso na prática muda a forma como você enxerga algo que, na teoria, já parecia resolvido.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Insertion-Sort).

---
