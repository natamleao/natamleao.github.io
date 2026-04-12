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

Alguns deles são simples. Outros são eficientes.

$$O(n^2)\; \text{vs}\; O(n\log n)$$.

Beleza. Isso quase todo mundo já viu.

Mas isso normalmente fica só na teoria.

Aqui a ideia foi ir além:

> colocar todos sob as mesmas condições e observar o comportamento real de execução

---

## Como montei o experimento

Nada muito “acadêmico”, mas com controle suficiente pra não distorcer os resultados:

todos os algoritmos recebem os mesmos dados
cada execução é isolada
medição com `clock_gettime` usando `CLOCK_MONOTONIC`
múltiplas execuções por entrada para reduzir ruído estatístico
uso de média, desvio padrão e coeficiente de variação (CV)

O coeficiente de variação (CV) — $\text{CV}=\frac{\sigma}{\mu}\times 100$ — é importante porque normaliza a dispersão em relação à média:

ele mostra o quanto o tempo oscila proporcionalmente ao valor médio

* $\sigma \to \text{desvio padrão}$
* $\mu \to \text{média}$

Isso evita uma armadilha comum:
desvio padrão parecer “grande” só porque o tempo médio também cresceu.

---

## Estrutura dos dados

Foi utilizada uma estrutura própria:

```c
struct _structureArray{
    float *_input_data;
    int _length;
};
````

Ela encapsula:

* dados dinâmicos (`float*`)
* tamanho do *array*

---

## *Benchmark*

Cada algoritmo não roda apenas uma vez.

O processo é:

1. o *array* original é gerado
2. são criadas **100 execuções independentes**
3. cada execução ordena uma cópia dos dados
4. calcula-se **média, desvio padrão e coeficiente de variação (CV) do tempo**

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
* Armazenamento: SSD
* Compilador: GCC com otimização `-O2`
* Flags: -O2 -Wall -Werror -fsanitize=address -g

Isso é necessário deixar claro, o tempo depende e vária de máquina para máquina.

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

### **Gráfico 1 — Tempo médio vs tamanho da entrada (escala log)**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - log-scale-time.svg"
       alt="Escala log"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Tempo médio em escala logarítmica para evidenciar crescimento assintótico
  </p>
</div>

Esse é o gráfico que revela o comportamento escondido.

A escala logarítmica faz duas coisas:

comprime os valores grandes
expõe padrões de crescimento

Aqui fica evidente:

crescimento quase linear no Quick Sort (em escala log)
crescimento acelerado no Bubble / Selection / Insertion Sort

Esse gráfico é o que mais aproxima prática e teoria.

---

### **Gráfico 2 — Desvio padrão vs tamanho da entrada**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - stddev-vs-input.svg"
       alt="Desvio padrão"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Variabilidade dos tempos de execução conforme o tamanho da entrada
  </p>
</div>

O desvio padrão mostra o quanto cada algoritmo varia entre execuções.

O que ele revela:

algoritmos simples tendem a ter mais variação em entradas grandes
algoritmos mais eficientes são mais estáveis
o custo não é só tempo médio — é previsibilidade

Isso importa porque um algoritmo instável pode ser ruim mesmo sendo rápido.

---

### **Gráfico 3 — Coeficiente de variação (CV) vs tamanho da entrada**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - cv-vs-input.svg"
       alt="Coeficiente de variação"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Relação entre dispersão e média dos tempos de execução
  </p>
</div>

Esse gráfico normaliza a variabilidade pelo tempo médio.

Ele responde uma pergunta mais profunda:

“qual algoritmo é mais confiável proporcionalmente ao seu custo?”

Aqui dá pra ver:

estabilidade relativa dos algoritmos eficientes
explosão de variabilidade nos quadráticos em grandes entradas

Esse é o gráfico mais “estatístico” da análise.

---

### **Gráfico 5 — Comparação empírica com complexidade assintótica**

<div style="text-align: center;">
  <img src="/assets/images/post-images/graphics/CS/graphic - asymptotic-comparison.svg"
       alt="Complexidade assintótica"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
  <p style="font-size: 0.9em; color: gray;">
    Comparação entre tempos reais e curvas teóricas O(n²) e O(n log n)
  </p>
</div>

Esse é o fechamento do experimento.

Aqui as curvas teóricas $O(n^2)$ e $O(n \log n)$ são ajustadas aos dados reais.

O objetivo não é bater valores exatos, mas sim:

comparar o formato de crescimento

E o resultado é claro:

Bubble Sort segue o comportamento quadrático
Quick Sort acompanha o crescimento linearítmico

Esse é o gráfico que valida a teoria na prática.

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

o tempo médio mostra o custo real
o desvio padrão mostra estabilidade
o CV mostra consistência relativa
o *log scale* revela padrões escondidos
a comparação teórica valida o modelo matemático

---

## Fechamento

A teoria não é uma abstração aqui — ela aparece nos dados.

Quando se mede corretamente:

> complexidade deixa de ser notação e vira comportamento observável

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Compare-Sorts).

---
