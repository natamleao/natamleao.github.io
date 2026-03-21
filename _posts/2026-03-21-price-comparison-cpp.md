---
layout: post
title: "Price Comparison CPP"
date: 2026-03-20
categories: portfolio
tags: [C++, Algorithms, Data Structures]
image: /assets/images/price-comparison-cpp-thumbnail.png
github: https://github.com/natamleao/Price-Comparison-CPP
excerpt: "Sistema em C++ para comparação de preços de ovos de Páscoa, com lista encadeada, modularização do código e automação da compilação com Makefile."
---

## Visão geral

Este projeto é uma implementação em **C++20** de um sistema simples para comparação de preços de ovos de Páscoa, construído em cima de uma **lista encadeada** como estrutura de dados principal. A proposta aqui não foi só fazer um menu funcionar, mas montar uma solução organizada, modular e fácil de manter. :contentReference[oaicite:1]{index=1}

A ideia central é prática: cadastrar produtos, manipular seus dados e analisar os valores para ajudar na decisão de compra. Simples no tema, mas forte no que ensina. :contentReference[oaicite:2]{index=2}

---

## O que foi construído

O projeto cobre o fluxo completo de um pequeno sistema de gerenciamento de dados:

- cadastro de itens;
- atualização de registros;
- remoção de elementos;
- exibição da lista;
- análise final para indicar se vale a pena comprar ou não. :contentReference[oaicite:3]{index=3}

Os itens armazenados são descritos no programa com **identificador** e **preço**, o que deixa o foco bem claro: manipular dados em uma estrutura encadeada e extrair uma decisão útil a partir deles. :contentReference[oaicite:4]{index=4}

---

## Por que esse projeto importa

Tem muita gente que quer pular direto para coisas “bonitas” e complexas, mas ignora o básico bem feito. E o básico, quando é bem feito, sustenta o resto. Aqui você trabalha ponteiros, encapsulamento, separação entre interface e implementação e organização de projeto em múltiplos diretórios. Isso vale ouro. :contentReference[oaicite:5]{index=5}

Além disso, o projeto mostra uma coisa importante: estrutura de dados não é só teoria de livro. Uma lista encadeada bem aplicada vira solução real para um problema pequeno, mas completo. :contentReference[oaicite:6]{index=6}

---

## Destaques técnicos

### Estrutura organizada
O projeto foi dividido em camadas e diretórios claros, com separação entre arquivos de cabeçalho, código-fonte, executáveis e objetos compilados. Essa organização deixa o código mais limpo e profissional. :contentReference[oaicite:7]{index=7}

### Lista encadeada como base
A escolha da lista encadeada faz sentido para o problema proposto, porque o sistema trabalha com inserção, remoção e atualização de nós de forma direta. Cada nó armazena identificador, preço e ponteiro para o próximo elemento. :contentReference[oaicite:8]{index=8}

### Automação com Makefile
A compilação é automatizada com `make`, o que facilita bastante a vida na hora de compilar, executar e limpar o projeto. É aquele detalhe que parece pequeno, mas separa projeto jogado de projeto organizado. :contentReference[oaicite:9]{index=9}

### Conceitos aplicados
O repositório explora manipulação de ponteiros, classes, modularização, separação de responsabilidades e organização de projeto em múltiplos arquivos. Isso dá uma base muito sólida para evoluir para estruturas e sistemas mais complexos. :contentReference[oaicite:10]{index=10}

---

## Funcionalidades

O sistema permite:

- adicionar um novo ovo de Páscoa à lista;
- atualizar apenas o identificador, apenas o preço ou ambos;
- remover um item pelo identificador;
- imprimir todos os itens cadastrados;
- verificar o resultado final e informar se compensa comprar. :contentReference[oaicite:11]{index=11}

Na prática, isso transforma o projeto em um mini sistema de cadastro e análise, com uma interface simples e direta. :contentReference[oaicite:12]{index=12}

---

## Como o projeto está estruturado

A estrutura do repositório segue esta lógica:

- `app/` — arquivos principais da aplicação;
- `bin/` — executáveis gerados;
- `include/` — arquivos de cabeçalho;
- `obj/` — arquivos objeto;
- `src/` — código-fonte;
- `Makefile` — regras de compilação. :contentReference[oaicite:13]{index=13}

Essa separação é um bom sinal de maturidade no projeto. Mesmo sendo um sistema pequeno, ele já evita aquela bagunça clássica de “um arquivo com tudo dentro”. :contentReference[oaicite:14]{index=14}

---

## Requisitos e execução

Para compilar e executar o projeto, o repositório informa que é necessário usar **GCC ou Clang com suporte a C++20**, além de **GNU Make**, em um ambiente **Linux ou macOS**. A compilação é feita com `make`, a execução com `make run` e a limpeza com `make clean` ou `make cleanapp`. :contentReference[oaicite:15]{index=15}

Esses comandos deixam o fluxo bem simples e prático para testar o projeto localmente. :contentReference[oaicite:16]{index=16}

---

## Conclusão

Esse projeto não tenta impressionar com firula. Ele faz o que precisa fazer, e faz do jeito certo: com estrutura, clareza e foco em fundamentos. E isso conta muito mais do que parecer sofisticado. :contentReference[oaicite:17]{index=17}

No fim, ele mostra domínio de base em C++ e de organização de código. E base boa é o tipo de coisa que não chama atenção só no começo — ela sustenta tudo o que vem depois. :contentReference[oaicite:18]{index=18}

---

## GitHub

Repositório: `natamleao/Price-Comparison-CPP` :contentReference[oaicite:19]{index=19}
