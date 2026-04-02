---
layout: post
title: "Comparando preços e organizando dados (em C++)"
date: 2026-03-14
categories: portfolio
mathjax: false
tags: [C++, Data Structures]
image: /assets/images/price-comparison-cpp-thumbnail.png
github: https://github.com/natamleao/Price-Comparison-CPP
excerpt: "Um pequeno sistema em C++ para organizar e comparar preços usando lista encadeada."
---

## A ideia por trás

Esse projeto surgiu como uma tentativa de sair do padrão “estrutura isolada” e montar algo mais próximo de um sistema completo — mesmo que simples.

A proposta foi direta:

> registrar dados, organizar esses dados e extrair alguma decisão deles

No caso, preços.

---

## Mais do que só armazenar

A estrutura em si não tem nada de especial: uma **lista encadeada**.

Mas aqui ela deixa de ser só exercício e passa a fazer parte de um fluxo:

* entrada de dados
* armazenamento
* manipulação
* avaliação
* saída

Isso muda o tipo de problema.

Você não está mais só implementando uma estrutura — está mantendo coerência ao longo de um ciclo completo.

---

## Onde o C++ entra de verdade

A principal diferença aqui não está na estrutura, mas na forma de organizar o código.

Usei **classes** para encapsular os dados e o comportamento.

Isso resolve algumas coisas de forma natural:

* evita acesso direto desnecessário
* agrupa responsabilidade
* reduz o número de funções soltas

Sem exagero — só o suficiente pra não virar bagunça.

---

## Um ponto que ficou claro

Mesmo num sistema pequeno, organização começa a importar rápido.

Quando você tem:

* inserção
* atualização
* remoção
* leitura
* processamento

…qualquer descuido começa a se propagar.

E é aí que a diferença entre “funciona” e “está bem estruturado” aparece.

---

## Sobre a escolha da lista encadeada

Não foi uma escolha por performance.

Foi uma escolha por simplicidade e controle:

* inserção e remoção diretas
* estrutura fácil de manter
* sem necessidade de redimensionamento

Para o problema, ela resolve sem complicar.

---

## Um detalhe interessante

A lógica de decisão (se vale a pena comprar ou não) é simples — e isso é intencional.

Ela serve mais como um “uso” dos dados do que como foco do sistema.

O objetivo aqui não era modelar economia, mas fechar o ciclo:
dados → processamento → resposta.

---

## O que esse projeto representa

Esse projeto fica num ponto intermediário interessante:

não é só estrutura de dados, mas também não é um sistema complexo.

É um passo na direção de juntar organização, fluxo e manipulação de dados em um único lugar.

---

## Fechamento

No fim, o código não é complicado.

Mas ele já exige um tipo diferente de cuidado — menos com o algoritmo isolado e mais com como tudo se conecta.

E esse tipo de mudança, mesmo em projetos pequenos, já altera bastante a forma de pensar.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Price-Comparison-CPP).

---
