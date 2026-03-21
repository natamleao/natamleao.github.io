---
layout: post
title: "Price Comparison CPP"
date: 2026-03-20
categories: portfolio
tags: [C++, Data Structures, Algorithms]
image: /assets/images/price-comparison-cpp-thumbnail.png
github: https://github.com/natamleao/Price-Comparison-CPP
excerpt: "Sistema em C++ para comparação de preços de ovos de Páscoa, com lista encadeada, modularização do código e automação da compilação com Makefile."
---

## Visão geral

Este projeto é uma implementação em **C++20** de um sistema simples para comparação de preços de ovos de Páscoa, usando **lista encadeada** como estrutura de dados principal. A proposta é construir um sistema organizado, modular e fácil de manter, com foco em aprendizado de fundamentos.

O objetivo central é prático: cadastrar produtos, manipular seus dados e analisar os valores para auxiliar na decisão de compra.

---

## O que foi construído

O projeto cobre o fluxo completo de um sistema de gerenciamento de dados:

* Cadastro de itens;
* Atualização de registros;
* Remoção de elementos;
* Exibição da lista;
* Análise final indicando se vale a pena comprar ou não.

Cada item possui **identificador** e **preço**, mantendo o foco em manipulação de dados em uma estrutura encadeada e extração de decisões úteis.

---

## Por que esse projeto importa

O básico bem feito sustenta todo o resto. Aqui você trabalha:

* Ponteiros;
* Encapsulamento;
* Separação entre interface e implementação;
* Organização de projeto em múltiplos diretórios.

Além disso, o projeto demonstra que estruturas de dados são aplicáveis: uma lista encadeada bem implementada resolve problemas reais, mesmo em sistemas pequenos.

---

## Destaques técnicos

### Estrutura organizada

Separação clara entre arquivos de cabeçalho, código-fonte, executáveis e objetos compilados, garantindo limpeza e profissionalismo.

### Lista encadeada

Permite inserção, remoção e atualização de nós de forma direta. Cada nó armazena identificador, preço e ponteiro para o próximo elemento.

### Automação com Makefile

Compilação, execução e limpeza automatizadas com `make`, garantindo fluxo eficiente e reproduzível.

### Conceitos aplicados

Manipulação de ponteiros, classes, modularização, separação de responsabilidades e organização em múltiplos arquivos. Base sólida para sistemas mais complexos.

---

## Funcionalidades

O sistema permite:

* Adicionar, atualizar ou remover itens;
* Imprimir todos os itens cadastrados;
* Avaliar o resultado final para informar se compensa comprar.

---

## Estrutura do projeto

* `app/` — arquivos principais da aplicação
* `bin/` — executáveis gerados
* `include/` — arquivos de cabeçalho
* `obj/` — arquivos objeto
* `src/` — código-fonte
* `Makefile` — regras de compilação

Essa organização evita bagunça e mostra maturidade no projeto, mesmo sendo pequeno.

---

## Como executar

1. Compilar: `make`
2. Executar: `make run`
3. Limpar: `make clean` ou `make cleanapp`

Requisitos: **GCC ou Clang (C++20)**, **GNU Make**, em **Linux ou macOS**.

---

## Conclusão

Projeto focado no fundamental: clareza, organização e boas práticas. Demonstra domínio de C++ básico e estrutura de código, criando uma base sólida para evoluir em sistemas mais complexos.

---

## GitHub

[https://github.com/natamleao/Price-Comparison-CPP](https://github.com/natamleao/Price-Comparison-CPP)
