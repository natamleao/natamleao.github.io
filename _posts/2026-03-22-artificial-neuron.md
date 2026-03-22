---
layout: post
title: "Artificial Neuron"
date: 2026-03-22
categories: notes
mathjax: true
tags: [Neural Networks, Machine Learning]
excerpt: "Neurônio artificial"
---

## O modelo de neurônio artificial

Inspirado no neurônio biológico, em 1943, [Warren Sturgis McCulloch](https://en.wikipedia.org/wiki/Warren_Sturgis_McCulloch) e [Walter Harry Pitts Jr.](https://en.wikipedia.org/wiki/Walter_Pitts) propuseram o neurônio artificial, que é ilustrado abaixo:

<div style="text-align: center;">
  <img src="/assets/images/post-images/neuronio-artificial.png"
       alt="Neurônio artificial"
       style="display: block; margin: 0 auto; max-width: 100%; width: 300px;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Neurônio artificial
  </p>
</div>

Análogo ao cérebro biológico, possui terminações sinápticas, um somatório que associa-se ao núcleo, e unidade de saída lembrando o papel dos dentritos. Nesse modelo, os sinais de entrada $x_1$, $x_2$, ..., $x_n$ são análogos aos impulsos elétricos do meio externo. As ponderações exercidas pelas terminações sinápticas do modelo biológico, são representadas no neurônio artificial pelos pesos sinápticos $v_1$, $v_2$, ..., $v_n$.

Assim como no neurônio biológico, a relevância da informação processada é dada pela multiplicação de $x_i$ por $v_i$. Assim a saída artificial do neurônio é a soma ponderada de suas entradas. O neurônio artificial é composto por sete elementos básicos:

<ol>
  <li>$\{x_1, x_2, ..., x_n\}$ — sinais de entrada</li>
  <li>$\{v_1, v_2, ..., v_n\}$ — pesos sinápticos</li>
  <li>$\sum$ — combinação linear</li>
  <li>$b$ — limiar de ativação </li>
  <li>$y_{in}$ — potencial de ativação</li>
  <li>$f$ — função de ativação</li>
  <li>$y$ — sinal de saída</li>
</ol>

---
