---
layout: post
title: "Comparando algoritmos de ordenação com análise estatística de desempenho"
date: 2026-04-06
categories: portfolio
mathjax: true
tags: [C, Algorithms, Sorting]
image: "/assets/images/sorts-comparison.png"
github: https://github.com/natamleao/Compare-Sorts
excerpt: "Análise comparativa de algoritmos de ordenação em C utilizando benchmarks estatísticos com múltiplas execuções, medição de variabilidade e isolamento de dados para garantir consistência experimental."
---

## A comparação é simples e evidencia a diferença teórica de complexidade

*Bubble Sort*, *Insertion Sort*, *Selection Sort*, *Quick Sort* e *Merge Sort* aparecem em introdução à computação.

Alguns deles são simples. Outros são eficientes $O(n^2)\; \text{vs}\; O(n\log n)$.

Beleza. Isso quase todo mundo já viu. Mas isso normalmente fica só na teoria.

Aqui a ideia foi ir além:

> colocar todos sob as mesmas condições e observar o comportamento real de execução

---

## Como montei o experimento

Nada muito “acadêmico”, mas com controle suficiente pra não distorcer os resultados:

- todos os algoritmos recebem os mesmos dados
- cada execução é isolada
- medição com `clock_gettime` usando `CLOCK_MONOTONIC`
- múltiplas execuções por entrada para reduzir ruído estatístico
- uso de média, desvio padrão e coeficiente de variação (CV)

O coeficiente de variação (CV) — $\text{CV}=\frac{\sigma}{\mu}\times 100$ — é importante porque normaliza a dispersão em relação à média:

ele mostra o quanto o tempo oscila proporcionalmente ao valor médio

* $\sigma \to \text{desvio padrão}$
* $\mu \to \text{média}$

Isso evita uma armadilha comum:
desvio padrão parecer “grande” só porque o tempo médio também cresceu.

---

## *Benchmark*

Cada algoritmo não roda apenas uma vez.

O processo é:

1. o *array* original é gerado
2. são criadas 100 execuções independentes
3. cada execução ordena uma cópia dos dados
4. calcula-se média, desvio padrão e coeficiente de variação (CV) do tempo

Isso reduz ruído e melhora confiabilidade da medição.

---

## Geração dos dados

Os valores são gerados aleatoriamente no intervalo: ```[-1e6, 1e6]```

E copiados para todos os algoritmos, garantindo:

* mesma distribuição
* mesma dificuldade
* comparação justa

---

## Ambiente de execução

* CPU: AMD Ryzen 7 5825U (8 cores / 16 threads)
* RAM: 7.2 GiB
* Sistema: Debian GNU/Linux 12 (Bookworm)
* Arquitetura: x86-64
* Compilador: GCC com otimização `-O2`
* Flags: `-O2 -Wall -Werror -fsanitize=address -g`

Isso é necessário deixar claro, o tempo depende e varia de máquina para máquina.

---

## Escalabilidade

Em entradas pequenas:

* tudo parece semelhante

Mas quando o tamanho cresce:

> a complexidade domina completamente o comportamento

---

## Resultados experimentais

Os resultados foram analisados sob três métricas principais:

* média do tempo de execução
* desvio padrão entre execuções
* coeficiente de variação (CV)

Essas métricas permitem avaliar não só o desempenho médio dos algoritmos, mas também a estabilidade das medições e a variabilidade relativa dos tempos.

---

## Gráficos de análise

Para os gráficos abaixo, os algoritmos $O(n^2)$ foram executados com os tamanhos de entrada: 10000, 20000, 50000, 100000 e 200000.
Já os algoritmos $O(n \log n)$ foram executados com os tamanhos: 10000, 20000, 50000, 100000, 200000, 500000 e 1000000.

### **Gráfico 1 — Tempo médio vs tamanho da entrada**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - log-scale-time.svg"
       alt="Escala log"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Tempo médio para evidenciar crescimento assintótico
  </p>
</div>

Neste gráfico, é possível observar claramente a diferença de escalabilidade entre os algoritmos.

*Merge Sort* e *Quick Sort* apresentam crescimento significativamente mais lento, mantendo tempos baixos mesmo com o aumento do tamanho da entrada, o que está em linha com a complexidade $O(n\log\,n)$.

Por outro lado, *Bubble Sort* e *Optimized Bubble Sort* exibem crescimento acentuado, característico de algoritmos $O(n^2)$. A otimização aplicada ao *Bubble Sort* não resulta em ganho relevante de desempenho para entradas grandes, indicando que melhorias locais não alteram o comportamento assintótico do algoritmo.

Além disso, observa-se que o *Quick Sort* é consistentemente o algoritmo mais rápido entre todos os testados, enquanto os algoritmos quadráticos tornam-se rapidamente inviáveis conforme o tamanho da entrada aumenta.

---

### **Gráfico 2 — Desvio padrão vs tamanho da entrada**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - stddev-vs-input.svg"
       alt="Desvio padrão"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Variabilidade dos tempos de execução conforme o tamanho da entrada
  </p>
</div>

Neste gráfico, observa-se o comportamento da variabilidade dos tempos de execução à medida que o tamanho da entrada aumenta.

Algoritmos como *Merge Sort* e *Quick Sort* apresentam uma tendência de estabilização do desvio padrão, indicando maior consistência nas execuções mesmo para entradas maiores. Isso sugere que, além de eficientes, esses algoritmos são também mais previsíveis.

Por outro lado, algoritmos quadráticos como *Bubble Sort*, *Optimized Bubble Sort*, *Insertion Sort* e *Selection Sort* exibem maior instabilidade, com picos mais elevados de desvio padrão e crescimento mais acentuado à medida que o tamanho da entrada aumenta.

Esse comportamento indica que, além de mais lentos, esses algoritmos também são menos consistentes, sofrendo maior influência de fatores como distribuição dos dados, cache e variações de execução.

---

### **Gráfico 3 — Coeficiente de variação (CV) vs tamanho da entrada**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - cv-vs-input.svg"
       alt="Coeficiente de variação"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Relação entre dispersão e média dos tempos de execução
  </p>
</div>

Neste gráfico, observa-se a relação entre a variabilidade e o tempo médio de execução dos algoritmos.

*Merge Sort* e *Quick Sort* apresentam valores baixos e relativamente estáveis, indicando comportamento consistente mesmo com o aumento do tamanho da entrada.

Por outro lado, os algoritmos quadráticos exibem maior variação relativa, especialmente em entradas maiores, evidenciando menor previsibilidade.

---

### **Gráfico 4 — Comparação empírica com complexidade assintótica**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - asymptotic-comparison.svg"
       alt="Complexidade assintótica"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Comparação entre tempos reais e curvas teóricas $O(n²)$ e $O(n\log\,n)$
  </p>
</div>

Neste gráfico, as curvas teóricas $O(n^2)$ e $O(n \log n)$ são ajustadas aos dados experimentais, permitindo a comparação direta entre comportamento real e crescimento assintótico.

Observa-se que o *Bubble Sort* acompanha de forma consistente a curva quadrática, apresentando crescimento mais acentuado à medida que o tamanho da entrada aumenta.

Já o *Quick Sort* segue de perto a curva $O(n\log\,n)$, mantendo crescimento significativamente mais controlado.

Essa correspondência evidencia que, apesar de abstrair constantes e detalhes de implementação, a análise assintótica descreve corretamente o comportamento dominante dos algoritmos na prática.

---

## Quando algoritmos deixam de ser opção

Algoritmos $O(n^2)$:

* crescem rapidamente
* tornam-se inviáveis em grandes entradas
* deixam de ser práticos muito cedo

Já $O(n \log n)$:

* escalam muito melhor
* continuam eficientes em grandes volumes

---

## O que fica evidente

* a teoria aparece no comportamento
* diferenças pequenas viram enormes
* o crescimento domina completamente o tempo de execução

---
## Síntese dos resultados

Quando os gráficos são vistos em conjunto:

- o tempo médio mostra o custo real
- o desvio padrão mostra estabilidade
- o CV mostra consistência relativa
- a escala logarítmica revela padrões de crescimento
- a comparação teórica valida o modelo matemático

---

## Fechamento

A teoria não é uma abstração aqui — ela aparece nos dados.

Quando se mede corretamente:

> complexidade deixa de ser notação e vira comportamento observável

---

## Leitura complementar

Uma análise complementar aprofunda o comportamento interno dos algoritmos a nível de CPU, utilizando `perf` para investigar IPC, *cache hierarchy* e *branch prediction*. Você pode encontrá-la [aqui](https://natamleao.github.io/complexity-vs-cpu-profiling/).

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Compare-Sorts).

---
