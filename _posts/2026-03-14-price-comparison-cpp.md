---
layout: post
title: "Price Comparison CPP"
date: 2026-03-14
categories: portfolio
mathjax: false
tags: [C++, Data Structures, Algorithms]
image: /assets/images/price-comparison-cpp-thumbnail.png
github: https://github.com/natamleao/Price-Comparison-CPP
excerpt: "Sistema em C++ para comparação de preços utilizando lista encadeada, com encapsulamento, modularização e automação de build."
---

![C++](https://img.shields.io/badge/Language-C++-blue)
![C++20](https://img.shields.io/badge/Standard-C++20-orange)
![Makefile](https://img.shields.io/badge/Build-Makefile-green)
![Data Structures](https://img.shields.io/badge/Data_Structures-Linked_List-yellow)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## Visão geral

Este projeto implementa um sistema em **C++20** para **comparação de preços**, utilizando **lista encadeada** como estrutura de dados principal.

A proposta é construir um sistema organizado e modular, explorando recursos da linguagem como **encapsulamento com classes**, ao mesmo tempo em que reforça fundamentos clássicos de estruturas de dados.

---

## O que foi implementado

O sistema permite:

- Inserir itens com identificador e preço  
- Atualizar dados existentes  
- Remover elementos da lista  
- Exibir todos os itens cadastrados  
- Avaliar os preços e indicar se vale a pena comprar  

O projeto cobre o ciclo completo de manipulação de dados em um sistema simples de linha de comando.

---

## Estrutura de dados

### Lista encadeada

Os dados são armazenados em uma **lista encadeada simples**, onde cada nó representa um item com:

- Identificador  
- Preço  
- Ponteiro para o próximo elemento  

Essa estrutura permite flexibilidade na manipulação dos dados, mantendo controle direto sobre a memória.

---

## Modelagem em C++

Diferente da versão em C, este projeto utiliza **classes** para representar os elementos da lista:

- Encapsulamento dos dados  
- Organização mais clara da lógica  
- Separação de responsabilidades  

Essa abordagem aproxima o código de práticas modernas de engenharia de software.

---

## Pipeline do sistema

O fluxo da aplicação segue:

1. Entrada de dados (inserção)  
2. Armazenamento em lista encadeada  
3. Manipulação (atualização, remoção)  
4. Processamento (análise de preços)  
5. Saída (exibição dos resultados)  

---

## Conceitos aplicados

Este projeto reforça conceitos importantes de C++:

- Encapsulamento com classes  
- Manipulação de ponteiros  
- Estruturas de dados encadeadas  
- Separação entre interface e implementação  
- Modularização do código  
- Organização de projeto em múltiplos diretórios  
- Automação de build com `Makefile`  

---

## Estrutura do projeto

```text
Price-Comparison-CPP/
│
├── app/              # Aplicação principal
├── bin/              # Executáveis
├── include/          # Cabeçalhos (.h)
├── obj/              # Arquivos objeto
├── src/              # Código-fonte (.cpp)
│
├── Makefile          # Build
├── README.md         # Documentação
└── LICENSE           # Licença MIT
````

---

## Como executar

```bash
git clone https://github.com/natamleao/Price-Comparison-CPP.git
cd Price-Comparison-CPP
make
make run
```

Para limpar:

```bash
make clean
make cleanapp
```

**Requisitos:** GCC ou Clang com suporte a C++20 e GNU Make em ambiente Linux/macOS.

---

## Conclusão

Este projeto demonstra a transição de C para C++, mantendo controle de baixo nível enquanto introduz conceitos de **abstração e organização orientada a objetos**.

Ele reforça fundamentos essenciais e mostra capacidade de estruturar código de forma mais robusta — um passo importante rumo a sistemas mais complexos.

---

[Veja o projeto completo no GitHub](https://github.com/natamleao/Price-Comparison-CPP)

---
