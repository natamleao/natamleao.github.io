---
layout: post
title: "Perceptron Neural Network"
date: 2026-03-22
categories: portfolio
tags: [Python, Neural Networks, Machine Learning]
image: /assets/images/perceptron-thumbnail.png
github: https://github.com/natamleao/Perceptron-Neural-Network
excerpt: "Implementação de um Perceptron em Python com pipeline completo: geração de dados, treinamento, avaliação e visualização da fronteira de decisão."
---

## Visão geral

Este projeto implementa um **Perceptron**, modelo fundamental do **Machine Learning**. O objetivo é construir um pipeline completo, testável e visual, desde a geração de dados até a análise da fronteira de decisão.

Entender este projeto significa compreender a base das redes neurais.

---

## O que foi construído

O ciclo completo de classificação inclui:

* Geração de datasets sintéticos;
* Pré-processamento e normalização;
* Treinamento supervisionado;
* Avaliação de desempenho;
* Visualização da fronteira de decisão;
* Testes automatizados com `pytest`.

O projeto evidencia que o Perceptron resolve apenas problemas **linearmente separáveis**, deixando claro seus limites.

---

## Por que esse projeto importa

Muita gente pula direto para redes neurais profundas sem dominar o básico.

O Perceptron ensina:

* Como um modelo aprende pesos;
* O que é uma fronteira de decisão;
* Por que linearidade importa;
* Onde modelos simples falham (XOR).

Essa compreensão é essencial para qualquer projeto sério de ML.

---

## Destaques técnicos

### Arquitetura modular

* `models/` → implementação do perceptron
* `training/` → lógica de treino
* `datasets/` → geração de dados
* `preprocessing/` → normalização
* `visualization/` → gráficos e fronteira de decisão
* `tests/` → validação com `pytest`

### Visualização da fronteira de decisão

Permite ver o modelo aprendendo a separar os dados, tornando conceitos abstratos intuitivos.

### Testes automatizados

Cobrem geração de dados, normalização, divisão treino/teste e comportamento esperado do modelo, elevando o nível do projeto.

---

## Experimentos

* AND, OR, XOR;
* datasets bidimensionais.

O destaque é aprender **onde o modelo falha**, mostrando limites do Perceptron e necessidade de redes mais profundas.

---

## Como executar

```bash
git clone https://github.com/natamleao/Perceptron-Neural-Network.git
cd Perceptron-Neural-Network
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python -m src.main
pytest -v
```

---

## Conclusão

O projeto demonstra **fundamentos bem feitos**: entender o Perceptron muda a forma de enxergar redes neurais, passando de uso de ferramenta para compreensão real do mecanismo por trás.

---

## GitHub

[https://github.com/natamleao/Perceptron-Neural-Network](https://github.com/natamleao/Perceptron-Neural-Network)

---
