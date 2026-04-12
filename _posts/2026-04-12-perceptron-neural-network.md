---
layout: post
title: "Perceptron: onde redes neurais começam (e param)"
date: 2026-04-12
categories: portfolio
mathjax: true
tags: [Python, Machine Learning, Neural Networks]
image: /assets/images/perceptron-thumbnail.png
github: https://github.com/natamleao/Perceptron-Neural-Network
excerpt: "Implementação de um perceptron em Python para entender como modelos lineares aprendem — e onde falham."
---

## O ponto de partida

O perceptron é um daqueles modelos que parecem simples demais à primeira vista.

Mas tem um detalhe importante:

> ele já contém a ideia essencial de aprendizado

Mesmo que de forma limitada.

---

## Mais do que um exercício

A implementação em si não tem mistério.

Um somatório, uma função de ativação, ajuste de pesos.

Mas a intenção aqui não foi só implementar.

Foi entender o comportamento:

* o que ele aprende
* como ele aprende
* onde ele simplesmente não consegue ir

---

## O modelo

A decisão do perceptron é baseada em uma combinação linear das entradas:

$$
y = \begin{cases}
\;\;\,1, & \text{se } \sum v_i x_i + b \ge 0 \\
-1, & \text{caso contrário}
\end{cases}
$$

Isso define uma fronteira de decisão — uma linha (ou hiperplano, em dimensões maiores).

É só isso.

Esse modelo deriva diretamente da ideia de neurônio artificial, que descrevi [aqui](https://natamleao.github.io/artificial-neuron).  

A função de ativação utilizada é um degrau bipolar. Também escrevi uma nota sobre isso [aqui](https://natamleao.github.io/activation-functions).

Durante o treinamento, os pesos são ajustados sempre que o modelo erra:

$$
\begin{cases}
v_i^{\text{novo}} = v_i^{\text{antigo}} + \alpha (t^{(k)} - y^{(k)}) x^{(k)} \\
b^{\text{novo}} = b^{\text{antigo}} + \alpha (t^{(k)} - y^{(k)})
\end{cases}
$$

Nada sofisticado — mas suficiente para capturar padrões simples.

---

## Onde ele funciona

Quando os dados podem ser separados por uma linha, ele converge.

Casos simples deixam isso claro:

* AND
* OR

Aqui, o modelo aprende rápido e se ajusta sem dificuldade.

---

## Onde ele quebra

O problema aparece quando a separação deixa de ser linear.

O exemplo clássico é o XOR.

Não importa o quanto você treine:

> o modelo não converge

E isso não é falha da implementação — é limitação do próprio modelo.

---

## O que isso mostra

Esse ponto é mais interessante do que parece.

Porque ele revela algo fundamental:

> o modelo não aprende “qualquer coisa” — ele aprende o que a sua forma permite

No caso do perceptron, essa forma é linear.

Se o problema exige algo além disso, ele simplesmente não consegue representar.

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

Ver isso acontecendo deixa o processo menos abstrato.

O modelo ajusta os pesos, move a fronteira e tenta corrigir erros — mas sempre dentro do que ele consegue representar.

---

## Por que esse projeto

A ideia aqui foi bem direta:

* sair da definição teórica
* implementar o aprendizado passo a passo
* visualizar o processo
* entender o limite do modelo na prática

---

## Fechamento

O perceptron é simples — e é justamente por isso que ele é útil.

Ele mostra o começo.

E também deixa claro onde esse começo deixa de ser suficiente.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Perceptron-Neural-Network).

---
