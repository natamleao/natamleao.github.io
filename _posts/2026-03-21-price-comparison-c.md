---
layout: post
title: "Price Comparison C"
date: 2026-03-21
categories: portfolio
tags: [C, Data Structures, Algorithms]
image: /assets/images/price-comparison-c-thumbnail.png
github: https://github.com/natamleao/Price-Comparison-C
excerpt: "Implementação em C de um sistema para comparação de preços de ovos de Páscoa usando lista encadeada e boas práticas de código."
---

## Visão geral

Este projeto é uma implementação em **C (padrão C11)** de um sistema simples para **comparar preços de ovos de Páscoa**, utilizando **lista encadeada** como estrutura de dados principal. A ideia é criar um sistema organizado e modular, praticando manipulação de ponteiros, organização de código e fundamentos sólidos da linguagem C. 

---

## O que foi construído

O sistema cobre todas as operações esperadas de um mini banco de dados em linha de comando:

* Adição de novos itens com identificador e preço;
* Atualização de identificador ou preço de itens existentes;
* Remoção de itens pelo identificador;
* Impressão da lista completa;
* Análise final indicando se vale a pena comprar. 

---

## Por que esse projeto importa

Esse tipo de projeto é um **termômetro de domínio dos fundamentos** em C. Ele mostra que você não só entende sintaxe, mas também:

* Alocação dinâmica de memória (`malloc` / `free`);
* Manipulação de ponteiros;
* Estruturas encadeadas;
* Separação entre *interface* e *implementação*;
* Modularização e organização de código. 

Mesmo que seja um programa “simples”, ele prova que você **sabe fazer as coisas do jeito certo** — e isso é o que distingue um código de hobby de um código de engenheiro.

---

## Destaques técnicos

### Estrutura modular

O projeto está dividido em diretórios lógicos:

* `app/` — arquivos de aplicação (main);
* `include/` — cabeçalhos `.h`;
* `src/` — código-fonte `.c`;
* `bin/`, `obj/` — artefatos de build;
* `Makefile` — automação da compilação. 

Essa divisão evita um “arquivo monolítico” e deixa o código escalável, legível e profissional.

### Lista encadeada

Cada nó armazena **identificador** e **preço**, com ponteiro para o próximo elemento, representando uma lista encadeada que adapta perfeitamente à necessidade de inserção, remoção e busca. 

---

## Funcionalidades

O programa permite:

* Inserir itens com identificador e preço;
* Atualizar dados de itens já cadastrados;
* Remover itens por identificador;
* Exibir a lista toda com preços;
* Avaliar os preços e indicar se é vantajoso comprar. 

---

### Exemplo de itens cadastrados

```text
ID | Preço
1  | R$ 14,00
2  | R$ 20,00
3  | R$ 25,00
```

## Como executar

Clone o repositório e compile com Make:

```bash
git clone https://github.com/natamleao/Price-Comparison-C.git
cd Price-Comparison-C
make
```

Execute:

```bash
make run
```

Limpe artefatos:

```bash
make clean
make cleanapp
```

Requisitos: **GCC ou Clang**, **GNU Make**, ambiente **Linux ou macOS**. 

---

## Conclusão

Esse projeto prova que você domina **fundamentos cruciais em C**: estruturas encadeadas, manipulação manual de memória e organização de código limpo. Não é glamouroso, mas é **base sólida — e é isso que sustenta coisas maiores depois**.

---

## GitHub

[https://github.com/natamleao/Price-Comparison-C](https://github.com/natamleao/Price-Comparison-C) 

---
