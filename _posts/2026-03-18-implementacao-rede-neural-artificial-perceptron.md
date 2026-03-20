---
layout: post
title: "Rede Neural Artificial Perceptron"
date: 2026-03-18
categories: portfolio
excerpt: "Implementação de uma Rede Neural Artificial Perceptron."
---

---

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Pytest](https://img.shields.io/badge/Tests-pytest-green)
![Status](https://img.shields.io/badge/Project-Personal-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)
 
---

## Sobre o projeto

> [!NOTE]
> Este projeto apresenta a implementação de uma **Rede Neural Artificial do tipo Perceptron**, proposta por [Frank Rosenblatt](https://en.wikipedia.org/wiki/Frank_Rosenblatt) em 1958.

O perceptron é um dos primeiros modelos de neurônio artificial e constitui a base histórica das áreas de:

- [Machine Learning](https://en.wikipedia.org/wiki/Machine_learning)
- [Artificial Neural Networks](https://en.wikipedia.org/wiki/Artificial_neural_network)

O objetivo deste projeto é demonstrar o funcionamento de um perceptron através de:

- geração de datasets
- treinamento supervisionado
- normalização de dados
- avaliação de desempenho
- visualização da fronteira de decisão

---

## Modelo matemático

> [!NOTE]
> O perceptron calcula uma combinação linear das entradas:

$y = \mathrm{sign}(w^T x + b)$

onde:

- $x$ representa o vetor de entradas  
- $w$ representa o vetor de pesos sinápticos  
- $b$ é o bias  
- $\mathrm{sign}(\cdot)$ é a função de ativação que define a classe da saída

> [!NOTE]
> Durante o treinamento, os pesos são atualizados pela seguinte regra de aprendizado:

$w_{t+1} = w_t + \eta\, y\, x$

onde:

- $\eta$ é a taxa de aprendizado  
- $y$ é o rótulo verdadeiro

---

## Funcionalidades

### 1. Implementação do Perceptron

> [!NOTE]
> O projeto implementa um perceptron de camada simples capaz de aprender problemas **linearmente separáveis** como:

- AND
- OR
- datasets sintéticos bidimensionais

> [!WARNING]
> Também demonstra a limitação clássica do perceptron ao tentar aprender o problema **XOR**, que não é linearmente separável.

> [!NOTE]
> Para os datasets booleanos (AND, OR, XOR), não é realizada divisão treino/teste,
> pois o número de amostras é muito pequeno. O objetivo desses experimentos é
> apenas demonstrar o comportamento teórico do perceptron.

#### Treinamento do Perceptron – classificação de regiões

O GIF mostra o treinamento do perceptron para classificar regiões como Norte (1) ou Sul (-1) com base em latitude e longitude.  
Como os dados não são linearmente separáveis, pontos verdes são corretos e vermelhos estão incorretos; a linha azul é a fronteira de decisão.

<p align="center">
  <img src="https://imgur.com/tu7jCk1.gif" width="450">
</p>

### 2. Pipeline de treinamento

> [!NOTE]
> O pipeline inclui:
> 
> - geração automática de datasets
> - divisão treino/teste
> - normalização com StandardScaler
> - treinamento do perceptron
> - cálculo de acurácia

### 3. Visualização da fronteira de decisão

> [!NOTE]
> Para datasets bidimensionais, o sistema gera gráficos mostrando a **fronteira de decisão aprendida pelo modelo**.
>
> Isso permite visualizar como o perceptron separa as classes no espaço de características.

---

## Estrutura do projeto

```
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

---

> [!IMPORTANT]
> ## Instalação

Clone o repositório:

```
git git@github.com:natamleao/Perceptron-Neural-Network.git
cd Perceptron-Neural-Network

```
Crie um ambiente virtual:

```
python -m venv venv

```
Ative o ambiente:

Linux / MacOS

```
source venv/bin/activate
```

Instale as dependências:

```
pip install -r requirements.txt
```
> [!IMPORTANT]
> ## Executar experimentos

Execute o pipeline completo:

```
python -m src.main
```

ou
```
chmod +x scripts/run_perceptron.sh
```

```
./scripts/run_perceptron.sh
```
> [!IMPORTANT]
> ## Testes automatizados

O projeto inclui testes automatizados utilizando [pytest](https://pytest.org).

Execute:

```
pytest -v
```
> [!NOTE]
> Os testes verificam:
> 
> - geração de datasets
> - carregamento de dados
> - normalização
> - divisão treino/teste
> - treinamento do perceptron
> - comportamento esperado em AND e XOR

## Resultados esperados

| Dataset | Comportamento esperado |
|--------|------------------------|
| AND | Acurácia próxima de 100% |
| OR | Acurácia próxima de 100% |
| XOR | Acurácia menor que 100% (problema não linearmente separável) |

> [!NOTE]
> O teste automatizado para o dataset XOR verifica apenas que a acurácia **não atinge 100%**, confirmando a limitação do perceptron para problemas não linearmente separáveis.

> [!WARNING]
> Isso demonstra a limitação fundamental do perceptron para problemas **não linearmente separáveis**.

---

> [!WARNING]
> ## Licença
>
> Este projeto está licenciado sob a **MIT License**.

---

## Autor

**Natam Leão Ferreira**

Conclusão: **2026**

---
