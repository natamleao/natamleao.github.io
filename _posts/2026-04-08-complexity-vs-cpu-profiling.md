---
layout: post
title: "O que a complexidade não mostra: análise de algoritmos com perf e CPU profiling"
date: 2026-04-08
categories: portfolio
mathjax: true
tags: [C, Algorithms, Profiling]
image: "/assets/images/perf-profiling.png"
github: https://github.com/natamleao/Compare-Sorts
excerpt: "Análise de algoritmos de ordenação a nível de CPU utilizando perf, explorando IPC, cache misses, branch prediction e comportamento real de execução."
---

## Complexidade teórica *vs* prática

A notação assintótica ($O(n)$, $O(n\log\,n)$, $O(n^2)$) descreve crescimento.

Mas não descreve **como o código realmente se comporta na CPU**.

Dois algoritmos com a mesma complexidade podem ter desempenhos completamente diferentes dependendo de:

- padrão de acesso à memória  
- *branch prediction*  
- hierarquia de *cache* (L1/L2/L3)  
- alocação dinâmica  
- chamadas de função  

Aqui entra o `perf`.

---

## O objetivo

A pergunta é simples:

> Se a complexidade já descreve tudo, por que o comportamento real na CPU muda tanto?

---

## Ferramenta usada: *perf*

O `perf` permite observar o que realmente acontece no *hardware*:

- ciclos de CPU  
- instruções executadas  
- IPC (*instructions per cycle*)  
- *branch misses*  
- *hotspots* por função  

Isso transforma a análise de teórica para física.

---

## Ambiente de execução

* CPU: AMD Ryzen 7 5825U (8 cores / 16 threads)
* RAM: 7.2 GiB
* Sistema: Debian GNU/Linux 12 (Bookworm)
* Arquitetura: x86-64
* Armazenamento: SSD
* Compilador: GCC com otimização `-O2`
- Flags: `-O2 -Wall -Werror -g`  

---

## Algoritmos analisados

- *Bubble Sort*  
- *Optimized Bubble Sort*  
- *Insertion Sort*  
- *Selection Sort*  
- *Merge Sort*  
- *Quick Sort*  

Todos executados sobre o mesmo conjunto de entrada.

---

## Métricas analisadas

O `perf stat` foi usado com:

```

cycles
instructions
branch-misses

```

E o perfil detalhado via `perf record + perf report`.

---

## Visão geral dos resultados

### IPC (*Instructions per Cycle*)

Algoritmos eficientes:

- *Quick Sort* $\to$ IPC mais baixo, mas execução rápida  
- *Merge Sort* $\to$ IPC moderado e estável  

Algoritmos $O(n²)$:

- *Bubble* / *Selection* / *Insertion Sort* $\to$ IPC variável, sem relação direta com eficiência

Importante: IPC alto não significa desempenho melhor. Ele só indica eficiência de pipeline.

---

## *Cache* e memória

### *Merge Sort*

- padrão de acesso sequencial  
- boa localidade de *cache*  
- uso intenso de `memcpy/memmove`  

Resultado:

- bom comportamento em *cache*  
- custo relevante de memória, não de CPU pura  

---

### *Quick Sort*

- melhor desempenho geral  
- comportamento depende da partição  
- acesso menos previsível à memória  

Apesar disso:

- baixa sobrecarga estrutural  
- boa performance média em dados aleatórios  

---

### *Bubble* / *Selection* / *Insertion Sort*

- muitas comparações repetidas  
- reuso intenso das mesmas regiões de memória  
- pouca exploração eficiente de *cache*  

Resultado:

- desperdício de ciclos  
- baixa eficiência global  
- crescimento explosivo com $n$  

---

## *Branch prediction* importa mais do que parece

Algoritmos com muitos condicionais:

- *Quick Sort* (`partition`)  
- *Bubble Sort* (comparações constantes)  

sofrem com:

- *branch misprediction*  
- *pipeline flush*  

Isso aparece diretamente no `branch-misses`.

---

## *Hotspots* reais (*perf report*)

Os principais pontos de execução:

- `merge`  
- `partition`  
- `insertionSort`  
- `bubbleSort`  

Em alguns casos:

> mais de 90% do tempo fica concentrado em uma única função

Conclusão direta:

> desempenho é sempre concentrado, nunca distribuído

---

## O que os dados mostram

Mesmo com a mesma complexidade:

- algoritmos se comportam diferente no *hardware*  
- memória pode dominar o custo total  
- chamadas internas podem ser gargalo dominante  

---

## Complexidade vs realidade

A teoria responde:

> quanto o algoritmo cresce

A CPU responde:

> onde o tempo realmente está sendo gasto

---

# Resultados com *perf*

---

## *Merge Sort*

- Tempo: ~23 ms  
- IPC: 1.21  
- *Branch misses*: 7.80%  
- *Cycles*: 92.4M  

*Hotspots*:

- `merge` → 73.69%  
- `memmove` → 9.24%  
- `malloc/free` → relevante  

comportamento dominado por memória

---

## *Quick Sort*

- Tempo: ~16 ms  
- IPC: 0.90  
- *Branch misses*: 12.54%  
- *Cycles*: 66.5M  

*Hotspots*:

- `partition` → 88.55%  

gargalo: previsibilidade de *branches*

---

## *Insertion Sort*

- Tempo: ~3.34 s  
- IPC: 4.77  
- *Branch misses*: ~0%  

*Hotspot*:

- `insertionSort` → 99.95%  

simples, mas extremamente ineficiente em escala

---

## *Selection Sort*

- Tempo: ~10.5 s  
- IPC: 4.90  
- *Branch misses*: ~0.01%  

*Hotspot*:

- `selectionSort` → 99.97%  

custo puramente $O(n²)$

---

## *Bubble Sort*

- Tempo: ~99 s  
- IPC: 0.41  
- *Branch misses*: 12.70%  

*Hotspot*:

- `bubbleSort` → 99.99%  

pior cenário clássico confirmado na prática

---

## *Optimized Bubble Sort*

- Tempo: ~98 s  
- IPC: 0.44  
- *Branch misses*: 12.71%  

*Hotspot*:

- `optimizedBubbleSort` → 99.99%  

otimização local irrelevante em termos assintóticos

---

## Leitura geral dos dados

### Algoritmos $O(n\log\,n)$

- melhor desempenho absoluto  
- melhor uso de CPU  
- melhor escalabilidade  

### Algoritmos $O(n²)$

- crescimento dominante  
- IPC não salva performance  
- custo explode rapidamente  

---

## O ponto mais importante

A diferença real não é só a complexidade:

- *Quick Sort* $\to$ sensível a *branch prediction*  
- *Merge Sort* $\to$ sensível a memória  
- *Bubble*/*Selection Sort* $\to$ redundância extrema  

Cada algoritmo falha por um motivo diferente no *hardware*.

---

## Conclusão

A complexidade continua correta.

Mas incompleta.

Na prática:

- *cache* muda o jogo  
- memória domina muitos algoritmos  
- *branch prediction* altera o desempenho real  
- IPC revela eficiência interna  

---

## Síntese final

> Dois algoritmos podem ter a mesma complexidade e comportamentos completamente diferentes na CPU.

---

## Leitura complementar

Uma análise complementar explora o comportamento estatístico dos algoritmos de ordenação com múltiplas execuções, medindo variabilidade, desvio padrão e consistência dos tempos de execução. Você pode encontrá-la [aqui](https://natamleao.github.io/sorting-benchmark/).

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Compare-Sorts).

---
