---
layout: post
title: "Perceptron Neural Network"
date: 2026-03-21
categories: portfolio
tags: [Python, Neural Networks, Machine Learning]
image: /assets/images/perceptron-thumbnail.png
github: https://github.com/natamleao/Perceptron-Neural-Network
excerpt: "Implementação de um Perceptron em Python com pipeline completo de dados, treinamento, visualização da fronteira de decisão e testes automatizados."
---

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Pytest](https://img.shields.io/badge/Tests-pytest-green)
![Status](https://img.shields.io/badge/Project-Personal-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

## Visão geral

Este projeto implementa um **Perceptron**, o modelo de rede neural mais básico (criador: Frank Rosenblatt, 1958). Trata-se do bloco fundamental de muitas técnicas de Machine Learning e Redes Neurais. Construir um perceptron do zero reforça conceitos essenciais, pois ele separa apenas problemas **linearmente separáveis**, resolvendo logicamente os casos clássicos como AND e OR, mas falhando no XOR (o que evidencia a necessidade de modelos multicamadas).

O objetivo foi montar um pipeline completo de classificação binária: gerar datasets sintéticos (AND, OR, bidimensionais), normalizá-los, treinar o perceptron supervisionado e avaliar seu desempenho. Além disso, o projeto destaca visualizações da fronteira de decisão aprendida e inclui uma suíte de testes automatizados (com Pytest) garantindo que cada parte do pipeline funcione corretamente.

## Destaques técnicos

- **Arquitetura modular:** o código está organizado em múltiplos diretórios (`data/`, `scripts/`, `src/config`, `datasets/`, `helpers/`, `models/`, `prediction/`, `preprocessing/`, `training/`, `visualization/`, `tests/`) e usa automação com scripts para facilitar execução e testes.
- **Implementação clássica do Perceptron:** aprendizado por combinação linear \(y = \mathrm{sign}(w^T x + b)\) e atualização de pesos \(w_{t+1} = w_t + \eta\,y\,x\).
- **Pipeline de dados completo:** geração de datasets sintéticos, divisão treino/teste, normalização (StandardScaler) e cálculo de acurácia para medir desempenho.
- **Visualização da fronteira de decisão:** gráficos exibem como o modelo separa as classes no espaço, tornando intuitivo o comportamento do perceptron em 2D.
- **Testes automatizados:** suíte com Pytest verifica geração de dados, pré-processamento, treinamento do perceptron e comportamento esperado nos problemas AND, OR e XOR.

## Funcionalidades

- Geração e carregamento de dados sintéticos para problemas clássicos (AND, OR, XOR e conjuntos bidimensionais).
- Treinamento supervisionado do perceptron e avaliação de sua acurácia em diferentes cenários.
- Exibição gráfica da fronteira de decisão aprendida pelo modelo em datasets bidimensionais.
- Conjunto de testes unitários (Pytest) cobrindo etapas-chave do pipeline de treinamento.
- Simulação de classificação de regiões (Norte/Sul) demonstrando o uso do perceptron em dados geográficos.

## Demonstração (Visualização)

A seguir, uma demonstração em vídeo do perceptron sendo treinado e mostrando a fronteira de decisão resultante para um conjunto de pontos bidimensionais:

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%;">
  <iframe 
    src="https://www.youtube.com/embed/Pk5vEqu2-FY" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen
    style="position: absolute; top:0; left:0; width:100%; height:100%;">
  </iframe>
</div>

## Modelo matemático

O perceptron calcula a saída como uma combinação linear das entradas:

\[ y = \mathrm{sign}(w^T x + b), \]

onde \(x\) é o vetor de características de entrada, \(w\) são os pesos sinápticos e \(b\) o bias. Durante o treinamento supervisionado, os pesos são ajustados pela regra:

\[ w_{t+1} = w_t + \eta \, y \, x, \]

onde \(\eta\) é a taxa de aprendizado e \(y\) o rótulo verdadeiro da amostra.

## Estrutura do projeto

```text
Perceptron-Neural-Network/
│
├── data/
│ ├── raw/            # datasets gerados
│ └── test/           # datasets usados nos testes
│
├── scripts/          # scripts para execução do projeto
│
├── src/              # código-fonte principal
│ ├── config/         # configurações do perceptron
│ ├── datasets/       # geração e manipulação de datasets
│ ├── helpers/        # funções auxiliares
│ ├── models/         # implementação do perceptron
│ ├── prediction/     # lógica de predição
│ ├── preprocessing/  # normalização e preparação dos dados
│ ├── training/       # pipeline de treinamento
│ └── visualization/  # visualização da fronteira de decisão
│
├── tests/            # testes automatizados (pytest)
│
├── requirements.txt  # dependências do projeto
├── README.md         # Documentação do projeto
└── LICENSE           # Licença do projeto
```

## Conclusão

Este projeto reforça conceitos fundamentais de aprendizado de máquina. Construir um perceptron do zero mostrou como os pesos são ajustados e como problemas linearmente separáveis são resolvidos, evidenciando por que perceptrons simples não resolvem o XOR e motivando a evolução para redes mais complexas. Em síntese, este trabalho demonstra domínio dos fundamentos de Machine Learning e da programação em Python, criando uma base sólida para projetos futuros mais avançados em inteligência artificial.

Confira o código completo no GitHub: `https://github.com/natamleao/Perceptron-Neural-Network`.

---
