---
layout: post
title: "Price Comparison C"
date: 2026-03-21
categories: portfolio
mathjax: false
tags: [C, Data Structures, Algorithms]
image: /assets/images/price-comparison-c-thumbnail.png
github: https://github.com/natamleao/Price-Comparison-C
excerpt: "Sistema em C para comparação de preços utilizando lista encadeada, com manipulação manual de memória e organização modular."
---

![C](https://img.shields.io/badge/Language-C-blue)
![C11](https://img.shields.io/badge/Standard-C11-orange)
![Makefile](https://img.shields.io/badge/Build-Makefile-green)
![Data Structures](https://img.shields.io/badge/Data_Structures-Linked_List-yellow)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## Visão geral

Este projeto implementa um sistema em **C (padrão C11)** para **comparação de preços**, utilizando **lista encadeada** como estrutura de dados principal.

A proposta é simples, mas direta: construir um sistema organizado e modular capaz de **armazenar, manipular e analisar dados**, reforçando fundamentos essenciais da linguagem C.

---

## O que foi implementado

O sistema permite:

- Inserir itens com identificador e preço  
- Atualizar identificador e/ou preço  
- Remover itens da lista  
- Exibir todos os dados cadastrados  
- Avaliar os preços e indicar se vale a pena comprar  

Mesmo sendo um sistema enxuto, ele cobre as principais operações de um **mini banco de dados em linha de comando**.

---

## Estrutura de dados

### Lista encadeada

Os dados são armazenados em uma **lista encadeada simples**, onde cada nó contém:

- Identificador  
- Preço  
- Ponteiro para o próximo elemento  

Essa estrutura permite inserções e remoções eficientes, além de manter o controle manual da memória.

---

## Modelo de análise

Após o cadastro dos itens, o sistema realiza uma análise simples dos preços e fornece um feedback indicando se a compra é vantajosa.

Essa etapa adiciona uma camada de **lógica de decisão**, indo além de um CRUD básico.

---

## Conceitos aplicados

Este projeto reforça fundamentos importantes de C:

- Alocação dinâmica de memória (`malloc`, `free`)  
- Manipulação de ponteiros  
- Estruturas encadeadas  
- Separação entre interface (`.h`) e implementação (`.c`)  
- Modularização do código  
- Organização de projeto em múltiplos diretórios  
- Automação de build com `Makefile`  

---

## Exemplo de dados

```text
ID | Preço
1  | R$ 14,00
2  | R$ 20,00
3  | R$ 25,00
````

---

## Pipeline do sistema

O fluxo da aplicação segue:

1. Entrada de dados (inserção)
2. Armazenamento em lista encadeada
3. Manipulação (atualização, remoção, busca)
4. Processamento (análise de preços)
5. Saída (exibição dos resultados)

---

## Estrutura do projeto

```text
Price-Comparison-C/
│
├── app/              # Aplicação principal
├── bin/              # Executáveis
├── include/          # Cabeçalhos (.h)
├── obj/              # Arquivos objeto
├── src/              # Código-fonte
│
├── Makefile          # Build
├── README.md         # Documentação
└── LICENSE           # Licença MIT
```

---

## Como executar

```bash
git clone https://github.com/natamleao/Price-Comparison-C.git
cd Price-Comparison-C
make
make run
```

Para limpar:

```bash
make clean
make cleanapp
```

**Requisitos:** GCC ou Clang (C11) e GNU Make em ambiente Linux/macOS.

---

## Conclusão

Este projeto demonstra domínio dos fundamentos essenciais de C, especialmente no uso de **ponteiros, memória dinâmica e estruturas de dados clássicas**.

Embora simples, ele evidencia a capacidade de construir sistemas organizados, modulares e com lógica aplicada — uma base sólida para projetos mais complexos.

---

[Veja o projeto completo no GitHub](https://github.com/natamleao/Price-Comparison-C)

---
