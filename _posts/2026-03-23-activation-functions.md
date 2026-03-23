---
layout: post
title: "Activation Functions"
date: 2026-03-23
categories: notes
mathjax: true
tags: [Neural Networks, Machine Learning]
excerpt: "Funções de ativação"
---

## Funções de ativação: controlador de sinal

O [neurônio artificial](https://natamleao.github.io/artificial-neuron/) processa o sinal de entrada, esse sinal de entrada é ponderado pelos pesos sinápticos e o bias, após isso, a função de ativação, limitará esse sinal ponderado a um intervalo controlado, indicando quanto dele passará para o(s) próximo(s) neurônio(s), o inibindo (limite inferior ou próximo dele do intervalo), o ativando (limite superior ou próximo dele do intervalo) ou o graduando (valor intermediário do intervalo). Dependendo da estratégia de treinamento, natureza dos dados, tipo de RNA, diferentes tipos de funções de ativação podem ser necessárias. Abaixo estão as mais clássicas.

### Função degrau binária

Está função tem uma alteração brusca nos valores de $y$ mudando sua saída para 0 ou 1, por isso o nome "binária".

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

### Função degrau bipolar

Nesta função, os valores de $y$ mudam para 1 ou -1, por isso nome "bipolar".

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

### Função gaussiana

Essa função tem uma aplicação específica nas redes neurais do tipo RBF (_Radial Basis Function_). Nesse tipo de rede, uma camada tem caráter de clusterização e para agrupamento dos dados faz use desse tipo de função de ativação.

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

### Função logística

A função logística tem $y$ limitado ao $(0, 1)$. Devido ao termo exponencial no denominador, ela tem subida bastante suave quando valores de $x$ aumentam. O ajuste do coeficiente $\beta$, interfere na curvatura, tornado sua suavidade maior ou menor.

<div style="display: flex; flex-direction: column; align-items: center;">

  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    
    <div>
      $$
      f(x) = \frac{1}{1 + e^{-\beta x}}
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

### Função rampa

Está função possui três partes, em duas delas é constante, enquanto na terceira é linear.

<div style="display: flex; flex-direction: column; align-items: center;">

  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    
    <div>
      $$
      f(x) = \begin{cases}
         a, & \text{se } x \gt a\\
         x, & \text{se } -a \le x \le a \\
        -a, & \text{se } x \lt a
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

### Função relu

Relu é a abreviação para “_Rectified linear unit_”. Para qualquer entrada negativa, a função retorna o valor 0 e para valores maiores ou iguais a 0, ela retonar o próprio valor. Essa função é muito empregada nas camadas intermediárias de redes densas do tipo _feedfoward_ como as redes MLP e Convolucionais, e também em camadas de convolução em redes Convolucionais.

<div style="display: flex; flex-direction: column; align-items: center;">

  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    
    <div>
      $$
      f(x) = \begin{cases}
         0, & \text{se } x \lt 0\\
         x, & \text{caso contrário}
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

### Função tagente hiperbólica

A função tagente hiperbólica tem $y\in(-1, 1)$. Ela possui curvatura muito semelhante a função logística e sua curvatura também é influenciada pela escolha do coeficiente $\beta$.

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
      <img src="/assets/images/post-images/funcoes-de-ativacao/tangente-hiperbolica.png"
           alt="Gráfico da função de ativação tagente hiperbólica"
           style="max-width: 100%; width: 250px;">
    </div>

  </div>

  <p style="font-size: 0.9em; color: gray; margin-top: 10px; text-align: center;">
    Função de ativação tagente hiperbólica
  </p>

</div>

---
