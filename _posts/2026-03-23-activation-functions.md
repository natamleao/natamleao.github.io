---
layout: post
title: "Activation Functions"
date: 2026-03-22
categories: notes
mathjax: true
tags: [Neural Networks, Machine Learning]
excerpt: "Funções de ativação"
---

<div style="display: flex; flex-direction: column; align-items: center;">

  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    
    <div>
      $$
      f(x) = \begin{cases}
         1, & \text{se } x \ge 0\\
         0, & \text{caso contrário}
      \end{cases}
      $$
    </div>

    <div>
      <img src="/assets/images/post-images/funcoes-de-ativacao/degrau-binaria.png"
           alt="Gráfico da função de ativação degrau binária"
           style="max-width: 100%; width: 250px;">
    </div>

  </div>

  <p style="font-size: 0.9em; color: gray; margin-top: 10px; text-align: center;">
    Função de ativação degrau binária
  </p>

</div>

<div style="display: flex; flex-direction: column; align-items: center;">

  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    
    <div>
      $$
      f(x) = \begin{cases}
         1, & \text{se } x \ge 0\\
        -1, & \text{caso contrário}
      \end{cases}
      $$
    </div>

    <div>
      <img src="/assets/images/post-images/funcoes-de-ativacao/degrau-bipolar.png"
           alt="Gráfico da função de ativação degrau bipolar"
           style="max-width: 100%; width: 250px;">
    </div>

  </div>

  <p style="font-size: 0.9em; color: gray; margin-top: 10px; text-align: center;">
    Função de ativação degrau bipolar
  </p>

</div>

<div style="display: flex; flex-direction: column; align-items: center;">

  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    
    <div>
      $$
      f(x) = e^{-\frac{(x - c)^2}{2\sigma^2}}
      $$
    </div>

    <div>
      <img src="/assets/images/post-images/funcoes-de-ativacao/gaussiana.png"
           alt="Gráfico da função de ativação gaussiana"
           style="max-width: 100%; width: 250px;">
    </div>

  </div>

  <p style="font-size: 0.9em; color: gray; margin-top: 10px; text-align: center;">
    Função de ativação gaussiana
  </p>

</div>

<div style="display: flex; flex-direction: column; align-items: center;">

  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    
    <div>
      $$
      \small
      \begin{aligned}
      f(x) &= \frac{1 - e^{-\beta x}}{1 + e^{-\beta x}} \\
           &\text{ou} \\
           &= \frac{2}{1 + e^{-\beta x}} - 1
      \end{aligned}
      $$
    </div>
    
    <div>
      <img src="/assets/images/post-images/funcoes-de-ativacao/logistica.png"
           alt="Gráfico da função de ativação logística"
           style="max-width: 100%; width: 250px;">
    </div>

  </div>

  <p style="font-size: 0.9em; color: gray; margin-top: 10px; text-align: center;">
    Função de ativação logística
  </p>

</div>

<div style="display: flex; flex-direction: column; align-items: center;">

  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    
    <div>
      $$
      f(x) = \begin{cases}
         1, & \text{se } x \ge 0\\
        -1, & \text{caso contrário}
      \end{cases}
      $$
    </div>

    <div>
      <img src="/assets/images/post-images/funcoes-de-ativacao/rampa.png"
           alt="Gráfico da função de ativação rampa"
           style="max-width: 100%; width: 250px;">
    </div>

  </div>

  <p style="font-size: 0.9em; color: gray; margin-top: 10px; text-align: center;">
    Função de ativação rampa
  </p>

</div>

<div style="display: flex; flex-direction: column; align-items: center;">

  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    
    <div>
      $$
      f(x) = \begin{cases}
         1, & \text{se } x \ge 0\\
        -1, & \text{caso contrário}
      \end{cases}
      $$
    </div>

    <div>
      <img src="/assets/images/post-images/funcoes-de-ativacao/relu.png"
           alt="Gráfico da função de ativação relu"
           style="max-width: 100%; width: 250px;">
    </div>

  </div>

  <p style="font-size: 0.9em; color: gray; margin-top: 10px; text-align: center;">
    Função de ativação relu
  </p>

</div>

<div style="display: flex; flex-direction: column; align-items: center;">

  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    
    <div>
      $$
      f(x) = \begin{cases}
         1, & \text{se } x \ge 0\\
        -1, & \text{caso contrário}
      \end{cases}
      $$
    </div>

    <div>
      <img src="/assets/images/post-images/funcoes-de-ativacao/tangente-hiperbolica.png"
           alt="Gráfico da função de ativação tagente hiperbólica"
           style="max-width: 100%; width: 250px;">
    </div>

  </div>

  <p style="font-size: 0.9em; color: gray; margin-top: 10px; text-align: center;">
    Função de ativação tagente hiperbólica
  </p>

</div>
