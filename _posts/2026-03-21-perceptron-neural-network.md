---
layout: post
title: "Perceptron Neural Network"
date: 2026-03-21
categories: portfolio
mathjax: true
tags: [Python, Neural Networks, Machine Learning]
image: /assets/images/perceptron-thumbnail.png
github: https://github.com/natamleao/Perceptron-Neural-Network
excerpt: "Implementação de um Perceptron em Python com pipeline de dados, treinamento, visualização da fronteira de decisão e testes automatizados."
---

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Pytest](https://img.shields.io/badge/Tests-pytest-green)
![ML](https://img.shields.io/badge/Machine_Learning-Basics-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## Visão geral

O **Perceptron**, proposto por Frank Rosenblatt em 1958, é um dos primeiros modelos de neurônio artificial e serve como base para redes neurais. Este modelo tem arquitetura feedforward de camada simples, ou seja, os sinais de entrada percorrem até a saída, sendo alterados pleos pesos sinápticos e bias, sem nenhum tipo de realimentação. Vale lembrar que as redes Perceptron admitem um vários neurônios de entrada, mas apenas um de saída.

Este projeto apresenta uma implementação do perceptron em Python, incluindo um pipeline simples de aprendizado supervisionado: geração de dados, pré-processamento, treinamento, avaliação e visualização.

---

## O que foi implementado

- Geração de datasets sintéticos (AND, OR, XOR e bidimensionais)
- Pré-processamento com normalização
- Treinamento supervisionado do perceptron
- Avaliação por acurácia
- Visualização da fronteira de decisão
- Testes automatizados com Pytest

---

## Modelo matemático

Antes de falarmos sobre o modelo matémático do Perceptron, quero falar sobre o neurônio artificial. O neurônio artificial foi proposto por McCulloch & Pitts (1943), é ilustrado abaixo:



O perceptron calcula a saída de acordo com a função degrau bipolar, que é a usada nesta implementação:

$$
y = \begin{cases}
   1, & \text{se } \sum v_i x_i + b \ge \text{limiar}\\
  -1, & \text{caso contrário}
\end{cases}
$$

### Função degrau bipolar

A função de ativação degrau bipolar é definida como:

$$
f(x) = \begin{cases}
   1, & \text{se } x \ge 0\\
  -1, & \text{caso contrário}
\end{cases}
$$

<div style="text-align: center;">
  <img src="/assets/images/post-images/funcao-degrau-bipolar.png"
       alt="Função degrau bipolar"
       style="display: block; margin: 0 auto; max-width: 100%; width: 250px;">
  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Gráfico da função de ativação degrau bipolar
  </p>
</div>


O algoritmo empregado para o treinamento neste tipo de RNA é o algoritmo da Regra de Hebb, é um algoritmo de treimamento supervisionado on-line, supervisionado porque já se tem categorias ou classes conhecidas de cada amostra e on-line porque os pesos sinápticos e bias são atualizados a cada época ou iteração, ou seja, a cada amostra do conjunto de amostras que produziu um erro. No algoritmo da Regra de Hebb a saída é comparada com a saíde desejada (targets) e então é ajusto os pesos sinápticos e bias ou não.

Durante o treinamento, os pesos sinápticos e o bias são atualizados por:

$$
\begin{cases}
v_i^{\text{novo}} = v_i^{\text{antigo}} + \alpha (t^{(k)} - y^{(k)}) x^{(k)} \\
b^{\text{novo}} = b^{\text{antigo}} + \alpha (t^{(k)} - y^{(k)})
\end{cases}
$$

<ul>
  <li>$v_i$ — </li>
  <li>$w$ — pesos</li>
  <li>$b$ — bias</li>
  <li>$\eta$ — taxa de aprendizado</li>
  <li>$y$ — rótulo verdadeiro</li>
</ul>

---

## Comportamento do modelo

O perceptron consegue aprender corretamente:

- AND  
- OR  
- conjuntos de dados linearmente separáveis  

No entanto, não consegue aprender:

- XOR  

Isso ocorre porque o modelo só representa fronteiras de decisão lineares.

---

## Demonstração

Treinamento do perceptron e evolução da fronteira de decisão:

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%;">
  <iframe 
    src="https://www.youtube.com/embed/Pk5vEqu2-FY" 
    frameborder="0" 
    allowfullscreen
    style="position: absolute; top:0; left:0; width:100%; height:100%;">
  </iframe>
</div>

---

## Pipeline de treinamento

O fluxo do projeto segue:

1. Geração de dados  
2. Divisão treino/teste  
3. Normalização (StandardScaler)  
4. Treinamento do modelo  
5. Avaliação  

---

## Resultados esperados

| Dataset | Resultado |
|--------|----------|
| AND | Acurácia próxima de 100% |
| OR | Acurácia próxima de 100% |
| XOR | Acurácia inferior a 100% |

---

## Estrutura do projeto

```text
Perceptron-Neural-Network/
│
├── data/
├── scripts/
├── src/
│   ├── models/
│   ├── training/
│   ├── preprocessing/
│   └── visualization/
├── tests/
├── requirements.txt
└── README.md
````

---

## Conclusão

Este projeto mostra, de forma direta, como o perceptron funciona e quais são suas limitações. Ele serve como base para entender modelos mais complexos de aprendizado de máquina.

---

[Veja o projeto completo no GitHub](https://github.com/natamleao/Perceptron-Neural-Network)

---
