---
layout: post
title: "Perceptron Neural Network"
date: 2026-03-20
categories: portfolio
tags: [Python, Neural Networks, Machine Learning]
image: /assets/images/perceptron-thumbnail.png
github: https://github.com/natamleao/Perceptron-Neural-Network
excerpt: "Implementação de um Perceptron em Python com pipeline completo: geração de dados, treinamento, avaliação e visualização da fronteira de decisão."
---

## Visão geral

Este projeto é uma implementação completa de um **Perceptron**, um dos modelos mais fundamentais da história do Machine Learning.

Aqui a ideia não foi só “fazer funcionar”, mas construir um pipeline organizado, testável e visual — desde a geração dos dados até a análise da fronteira de decisão.

Se você entende bem esse projeto, você entende a base de redes neurais.

---

## O que foi construído

O projeto cobre o ciclo completo de um modelo de classificação:

- geração de datasets sintéticos;
- pré-processamento e normalização;
- treinamento supervisionado;
- avaliação de desempenho;
- visualização da fronteira de decisão;
- testes automatizados com `pytest`.

Além disso, ele explora um ponto crucial:

> O Perceptron só resolve problemas **linearmente separáveis**.

E isso fica claro nos experimentos.

---

## Demonstração

Execução real do projeto, mostrando o conjunto de dados e a fronteira de decisão aprendida:

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%;">
  <iframe 
    src="https://www.youtube.com/embed/Pk5vEqu2-FY" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen
    style="position: absolute; top:0; left: 0; width: 100%; height: 100%;">
  </iframe>
</div>

---

## Por que esse projeto importa

Muita gente pula direto pra redes neurais profundas sem entender o básico.

Isso é erro.

O Perceptron é o "átomo" das redes neurais. Ele ensina:

- como um modelo aprende pesos;
- o que é uma fronteira de decisão;
- por que linearidade importa;
- onde modelos simples quebram.

E quando ele quebra (tipo no XOR), você começa a entender por que redes mais profundas existem.

---

## Destaques técnicos

### Arquitetura organizada
O projeto não é um script solto. Ele foi dividido em módulos:

- `models/` → implementação do perceptron  
- `training/` → lógica de treino  
- `datasets/` → geração de dados  
- `preprocessing/` → normalização  
- `visualization/` → gráficos e fronteira de decisão  
- `tests/` → validação com pytest  

Isso já coloca o projeto em outro nível comparado a implementações básicas.

---

### Visualização da fronteira de decisão
Um dos pontos mais fortes do projeto.

Você consegue literalmente ver o modelo aprendendo a separar os dados — isso transforma um conceito abstrato em algo visual e intuitivo.

---

### Testes automatizados
Inclui testes para:

- geração de datasets;
- normalização;
- divisão treino/teste;
- comportamento esperado do modelo.

Pouca gente coloca isso em projeto de ML. Isso aqui conta muito.

---

## Experimentos

Foram testados cenários clássicos:

- AND  
- OR  
- datasets bidimensionais  
- XOR (para mostrar limitação)

O resultado mais importante não é quando ele acerta.

É quando ele falha — porque ali você entende o limite do modelo.

---

## Como executar

Clone o repositório:

```bash
git clone https://github.com/natamleao/Perceptron-Neural-Network.git
````

Entre na pasta:

```bash
cd Perceptron-Neural-Network
```

Crie ambiente virtual:

```bash
python -m venv venv
source venv/bin/activate
```

Instale dependências:

```bash
pip install -r requirements.txt
```

Execute:

```bash
python -m src.main
```

Rodar testes:

```bash
pytest -v
```

---

## Conclusão

Esse projeto não é sobre complexidade.

É sobre **fundamento bem feito**.

Entender o Perceptron direito muda completamente como você enxerga redes neurais. Você deixa de decorar e começa a enxergar o mecanismo por trás.

E, na prática, isso separa quem só usa ferramenta de quem realmente entende o que está fazendo.

---

## GitHub

[https://github.com/natamleao/Perceptron-Neural-Network](https://github.com/natamleao/Perceptron-Neural-Network)

---
