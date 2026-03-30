---
layout: post
title: "Perceptron: onde redes neurais começam (e param)"
date: 2026-03-30
categories: portfolio
mathjax: true
tags: [Python, Machine Learning]
image: /assets/images/perceptron-thumbnail.png
github: https://github.com/natamleao/Perceptron-Neural-Network
excerpt: "Implementação de um perceptron em Python para entender como modelos lineares aprendem — e onde falham."
---

## Ideia

O perceptron é um modelo simples, mas importante.

Ele resolve um problema básico:  
> separar dados em duas classes usando uma fronteira linear

E ao mesmo tempo deixa claro onde isso deixa de funcionar.

---

## O que foi feito

Implementei um perceptron em Python com um fluxo completo:

- geração de dados (AND, OR, XOR e 2D)  
- pré-processamento  
- treinamento supervisionado  
- avaliação  
- visualização da fronteira de decisão  

Sem usar frameworks prontos — só o modelo na mão.

---

## O modelo

A decisão do perceptron é baseada em uma combinação linear das entradas:

$$
y = \begin{cases}
\;\;1, & \text{se } \sum v_i x_i + b \ge 0 \\
-1, & \text{caso contrário}
\end{cases}
$$

Esse modelo deriva diretamente da ideia de neurônio artificial, que descrevi [aqui](https://natamleao.github.io/artificial-neuron).  

A função de ativação utilizada é um degrau bipolar. Também escrevi uma nota sobre isso [aqui](https://natamleao.github.io/activation-functions).

Durante o treinamento, os pesos são ajustados sempre que o modelo erra:

$$
\begin{cases}
v_i^{\text{novo}} = v_i^{\text{antigo}} + \alpha (t^{(k)} - y^{(k)}) x^{(k)} \\
b^{\text{novo}} = b^{\text{antigo}} + \alpha (t^{(k)} - y^{(k)})
\end{cases}
$$

Nada muito sofisticado — mas suficiente para aprender padrões simples.

---

## O ponto central

O perceptron funciona bem quando os dados são **linearmente separáveis**.

Exemplos:

- AND  
- OR  

Mas falha em casos como:

- XOR  

Porque não existe uma linha que separe corretamente os dados.

Esse limite é importante — ele mostra por que modelos mais complexos surgiram.

---

## Visualização

A parte mais interessante é ver a fronteira de decisão se ajustando ao longo do treino.

<div style="width: 100%;">
  <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
    <iframe 
      src="https://www.youtube.com/embed/Pk5vEqu2-FY" 
      frameborder="0" 
      allowfullscreen
      style="position: absolute; top:0; left:0; width:100%; height:100%;">
    </iframe>
  </div>
</div>

---

## Um detalhe importante

Esse projeto deixa evidente uma coisa:

> aprender não significa entender qualquer padrão

O modelo só aprende aquilo que cabe dentro da forma que ele consegue representar.

No caso do perceptron: linhas.

---

## Por que esse projeto

A ideia aqui foi:

- entender o funcionamento básico de redes neurais  
- implementar o treinamento manualmente  
- visualizar como o modelo aprende  
- observar onde ele falha  

---

## Código

O projeto completo está disponível [aqui](https://github.com/natamleao/Perceptron-Neural-Network)

---
