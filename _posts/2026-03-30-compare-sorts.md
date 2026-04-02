---
layout: post
title: "Comparando Heap Sort e Insertion Sort: tempo real"
date: 2026-03-30
categories: portfolio
mathjax: true
tags: [C, Algorithms, Sorting]
image: "/assets/images/heap-vs-insertion.png"
github: https://github.com/natamleao/Compare-Sorts
excerpt: "Comparação prática entre Heap Sort e Insertion Sort em C com medição de tempo, mostrando o custo real de cada algoritmo."
---

## A comparação que todo mundo já viu — mas que muda quando você mede

*Heap Sort* e *Insertion Sort* aparecem juntos em qualquer curso básico.

Um é eficiente, outro é simples.
$O(nlog\,n)\; \text{vs}\; O(n²)$.

Beleza. Isso é o esperado.

Mas esse tipo de comparação costuma parar na teoria.
Aqui a ideia foi empurrar um pouco além:

> colocar os dois sob as mesmas condições e observar o que acontece de verdade

---

## Como montei o experimento

Nada muito elaborado — mas com cuidado suficiente pra não enviesar o resultado:

* os dois algoritmos recebem **exatamente os mesmos dados**
* cada um roda isoladamente
* medição com `clock_gettime` usando `CLOCK_MONOTONIC`
* foco direto em tempo de execução

A intenção não foi fazer *benchmark* acadêmico, mas também não deixar solto.

---

## Estruturas

Cada algoritmo roda na sua própria estrutura, bem direta:

* *Heap Sort* com *heap* em *array*
* *Insertion Sort* com array dinâmico

Isso evita interferência entre implementações e mantém a comparação limpa.

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

Isso importa mais do que parece.
Tempo de execução não é absoluto — ele depende diretamente de onde você roda.

---

## O que aparece quando você começa a escalar

Com entradas pequenas, os dois algoritmos convivem bem.

O *Insertion Sort* até se mantém competitivo — o que faz sentido, já que ele tem baixo overhead.

Mas conforme o tamanho cresce, a diferença deixa de ser sutil.

Ela começa a ficar estrutural.

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

O crescimento é consistente.
Nada surpreendente — mas também nada fora de controle.

---

* **Gráfico 2:** *Insertion Sort* — crescimento do tempo de execução

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/Gráfico - Insertion Sort.svg"
       alt="Gráfico Insertion Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Insertion Sort — crescimento acelerado do tempo (escala log)
  </p>
</div>

Aqui a coisa muda.

O crescimento começa aceitável, mas rapidamente perde controle.
O comportamento quadrático aparece sem disfarce.

---

* **Gráfico 3:** *Heap Sort* vs *Insertion Sort* — comparação direta

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/Gráfico - Heap Sort vs Insertion Sort.svg"
       alt="Comparação Heap Sort vs Insertion Sort"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Heap Sort vs Insertion Sort — diferença de crescimento (escala log)
  </p>
</div>

Colocados lado a lado, não é mais uma questão de “qual é melhor”.

É uma questão de **qual continua sendo viável**.

---

## O ponto em que a teoria vira limite real

Teve um momento no experimento que deixou isso bem claro.

Ao tentar escalar para 50 milhões de elementos, o *Insertion Sort* simplesmente deixou de ser uma opção prática.

Não por detalhe de implementação, mas por natureza do algoritmo.

A conta é direta: $(5 \times 10^7)^2 = 2.5 \times 10^{15}$

Mesmo com operações rápidas, isso escala para tempos absurdos.

É aqui que $O(n²)$ deixa de ser só uma notação e vira uma barreira concreta.

---

## O que ficou mais evidente

Algumas coisas que já eram conhecidas ficam bem mais claras quando você mede:

* *Heap Sort* mantém crescimento controlado
* *Insertion Sort* degrada rápido com escala
* a diferença não é só teórica — é operacional
* viabilidade depende diretamente da complexidade

E talvez o mais importante:

> existe um ponto onde o algoritmo deixa de ser “lento” e passa a ser simplesmente inviável

---

## Fechamento

Esse projeto não tenta reinventar nada.

Ele só coloca dois algoritmos clássicos no mesmo cenário e observa o comportamento com dados reais.

E quando você faz isso, a diferença entre eles deixa de ser um detalhe acadêmico.

Vira uma decisão prática.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Compare-Sorts).

---
