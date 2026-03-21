---
layout: post
title: "Perceptron Neural Network — Case Study"
date: 2026-03-21
categories: portfolio
tags: [Python, Neural Networks, Machine Learning, AI]
image: /assets/images/perceptron-thumbnail.png
github: [https://github.com/natamleao/Perceptron-Neural-Network](https://github.com/natamleao/Perceptron-Neural-Network)
excerpt: "Implementação completa de um Perceptron em Python com pipeline de dados, treinamento, visualização de fronteira de decisão e testes automatizados — um case de Machine Learning do zero."
---

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Pytest](https://img.shields.io/badge/Tests-pytest-green)
![ML](https://img.shields.io/badge/Machine_Learning-Basics-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## ⚡ Visão Geral

O **Perceptron**, criado por **Frank Rosenblatt (1958)**, é a base das redes neurais. Resolve problemas **linearmente separáveis** (AND, OR) e evidencia limitações em problemas não lineares (XOR), mostrando a necessidade de redes multicamadas.

Este projeto implementa um **pipeline completo de classificação binária**: geração de datasets, pré-processamento, treinamento supervisionado, visualização da fronteira de decisão e testes automatizados.

> 💡 Construir um Perceptron do zero é fundamental para dominar Machine Learning.

---

## 🛠️ Destaques Técnicos

* **Arquitetura Modular:** `data/`, `scripts/`, `src/`, `tests/`
* **Regra do Perceptron:**
  [
  y = \mathrm{sign}(w^T x + b), \quad w_{t+1} = w_t + \eta,y,x
  ]
* **Pipeline Completo:** geração de dados, divisão treino/teste, normalização, avaliação de acurácia
* **Visualização:** gráficos da fronteira de decisão 2D
* **Testes Automatizados:** Pytest cobrindo todas as etapas do pipeline

---

## 📊 Funcionalidades

* ✅ Geração de datasets clássicos: AND, OR, XOR, bidimensionais
* ✅ Treinamento supervisionado com cálculo de acurácia
* ✅ Visualização da fronteira de decisão
* ✅ Testes unitários automatizados
* ✅ Aplicação em dados geográficos (ex: Norte/Sul)

---

## 🎬 Demonstração

Treinamento do Perceptron e fronteira de decisão em tempo real:

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%;">
  <iframe 
    src="https://www.youtube.com/embed/Pk5vEqu2-FY" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen
    style="position: absolute; top:0; left:0; width:100%; height:100%;">
  </iframe>
</div>

> ⚡ A visualização mostra claramente como o perceptron separa as classes no espaço 2D.

---

## 📐 Modelo Matemático

O Perceptron calcula a saída como:

[
y = \mathrm{sign}(w^T x + b)
]

Durante o treinamento, os pesos são ajustados pela regra:

[
w_{t+1} = w_t + \eta , y , x
]

* (x) = vetor de entrada
* (w) = pesos
* (b) = bias
* (\eta) = taxa de aprendizado
* (y) = rótulo verdadeiro

> ⚡ Cada atualização aproxima o modelo da fronteira ideal entre classes.

---

## 💻 Estrutura do Projeto

```text
Perceptron-Neural-Network/
│
├── data/             # datasets gerados e de teste
├── scripts/          # scripts de execução
├── src/              # código-fonte principal
│   ├── config/       # configurações
│   ├── datasets/     # geração/manipulação de datasets
│   ├── helpers/      # funções auxiliares
│   ├── models/       # implementação do perceptron
│   ├── prediction/   # lógica de predição
│   ├── preprocessing/# normalização/preparação
│   ├── training/     # pipeline de treinamento
│   └── visualization/# gráficos da fronteira de decisão
├── tests/            # Pytest
├── requirements.txt  # dependências
├── README.md         # documentação
└── LICENSE           # MIT
```

---

## 🔍 Conclusão

Construir um **Perceptron do zero**:

* Ensina conceitos fundamentais de Machine Learning
* Evidencia limites de modelos lineares (XOR)
* Cria base para redes multicamadas e Deep Learning

> 🚀 Um case completo de **Python, ML, visualização e testes automatizados**, perfeito para portfólio técnico profissional.

[🔗 Veja o projeto completo no GitHub](https://github.com/natamleao/Perceptron-Neural-Network)

---
