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

O **Perceptron**, proposto por Frank Rosenblatt em 1958, é um dos primeiros modelos de neurônio artificial e serve como base para redes neurais. Este modelo tem arquitetura feedforward de camada simples, ou seja, os sinais de entrada percorrem até a saída, sendo alterados pelos pesos sinápticos e bias, sem nenhum tipo de realimentação. O perceptron pode receber múltiplas entradas, mas produz apenas uma saída.

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

O modelo matemático do Perceptron, por ser uma RNA, segue a construção do [neurônio artificial](https://natamleao.github.io/artificial-neuron/), abaixo é apresentada a versão com a função de ativação degrau bipolar (para ver mais sobre funções de ativação, acesse: [Activation Function](https://natamleao.github.io/artificial-neuron/)):

$$
y = \begin{cases}
   1, & \text{se } \sum v_i x_i + b \ge \text{limiar}\\
  -1, & \text{caso contrário}
\end{cases}
$$

Obs: o limiar é ponto de decisão da função de ativação.

### Função degrau bipolar

A função de ativação degrau bipolar é definida como:

<div style="display: flex; justify-content: center; align-items: center; gap: 40px;">

  <div>
    $$
    f(x) = \begin{cases}
       1, & \text{se } x \ge 0\\
      -1, & \text{caso contrário}
    \end{cases}
    $$
  </div>

  <div style="text-align: center;">
    <img src="/assets/images/post-images/funcoes-de-ativacao/degrau-bipolar.png"
         alt="Gráfico da função de ativação degrau bipolar"
         style="max-width: 100%; width: 250px;">
    <p style="font-size: 0.9em; color: gray;">
      Gráfico da função de ativação degrau bipolar
    </p>
  </div>

</div>

O algoritmo empregado para o treinamento neste tipo de RNA é o algoritmo da Regra de Hebb, é um algoritmo de treinamento supervisionado on-line, supervisionado porque já se tem categorias ou classes conhecidas de cada amostra e on-line porque os pesos sinápticos e bias são atualizados a cada época ou iteração, ou seja, a cada amostra do conjunto de amostras que produziu um erro. No algoritmo da Regra de Hebb a saída é comparada com a saída desejada (targets) e então é ajusto os pesos sinápticos e bias ou não.

Durante o treinamento, os pesos sinápticos e o bias são atualizados por:

$$
\begin{cases}
v_i^{\text{novo}} = v_i^{\text{antigo}} + \alpha (t^{(k)} - y^{(k)}) x^{(k)} \\
b^{\text{novo}} = b^{\text{antigo}} + \alpha (t^{(k)} - y^{(k)})
\end{cases}
$$

Componentes na equação de atualização de pesos sinápticos:

<ul>
  <li>$v_i^{\text{novo}}$ — o novo valor do peso sináptico i</li>
  <li>$v_i^{\text{antigo}}$ — o antigo valor do peso sináptico i</li>
  <li>$\alpha$ — a taxa de aprendizado</li>
  <li>$t^{(k)}$ — o valor esperado (target) para a saída da amostra k</li>
  <li>$y^{(k)}$ — a saída da amostra k</li>
  <li>$x^{(k)}$ — a entrada da amostra k</li>
</ul>

Componentes na equação de atualização do bias (limiar de ativação):

<ul>
  <li>$b^{\text{novo}}$ — o novo valor do bias</li>
  <li>$b^{\text{antigo}}$ — o antigo valor do bias</li>
  <li>$\alpha$ — a taxa de aprendizado</li>
  <li>$t^{(k)}$ — o valor esperado (target) para a saída da amostra k</li>
  <li>$y^{(k)}$ — a saída da amostra k</li>
</ul>

---

## Comportamento do modelo

O perceptron consegue aprender corretamente:

- AND  
- OR  
- conjuntos de dados linearmente separáveis  

No entanto, não consegue aprender:

- XOR  

Isso ocorre porque o modelo só representa fronteiras de decisão lineares. Esse limite motivou o desenvolvimento das redes multicamadas (MLPs), que superam essa limitação ao introduzir não-linearidade.

---

## Demonstração

Treinamento do perceptron e evolução da fronteira de decisão:

<div style="width: 100%;">

  <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
    <iframe 
      src="https://www.youtube.com/embed/Pk5vEqu2-FY" 
      frameborder="0" 
      allowfullscreen
      style="position: absolute; top:0; left:0; width:100%; height:100%;">
    </iframe>
  </div>

  <p style="font-size: 0.9em; color: gray; text-align: center;">
    Treinamento do perceptron e evolução da fronteira de decisão
  </p>

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

Apesar de simples, o perceptron marca o início das redes neurais modernas. Entender suas limitações é essencial para compreender por que arquiteturas mais profundas foram desenvolvidas.

---

[Veja o projeto completo no GitHub](https://github.com/natamleao/Perceptron-Neural-Network)

---
