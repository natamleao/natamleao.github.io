---
layout: post
title: "Comparando preços com controle manual (em C)"
date: 2026-03-18
categories: portfolio
mathjax: false
tags: [C, Data Structures]
image: /assets/images/price-comparison-c-thumbnail.png
github: https://github.com/natamleao/Price-Comparison-C
excerpt: "Sistema em C para manipulação e análise de preços com controle manual de memória."
---

## Voltando um nível abaixo

Depois de fazer a versão em C++ (clique [aqui](https://natamleao.github.io/price-comparison-cpp/) para vê-la), esse projeto foi quase um “desmonte”.

Mesma ideia geral — comparar preços — mas tirando tudo que a linguagem resolve por você.

Sem classes, sem abstração forte, sem proteção.

Só C direto.

---

## O problema em si 

A ideia é simples: registrar preços e tomar uma decisão básica — vale a pena comprar ou não.

Mas o interessante não está na regra de decisão.

Está em como organizar isso sem apoio da linguagem.

* armazenar itens
* atualizar dados
* remover elementos
* percorrer e analisar

Tudo isso com controle explícito.

---

## A estrutura escolhida

Usei uma **lista encadeada simples**.

Nada além do necessário.

Ela resolve bem inserção e remoção, mantém o código enxuto e não força nenhuma complexidade artificial.

É o tipo de escolha que não chama atenção — e isso é bom.

---

## Onde o C pesa mais

Comparando com a versão em C++, a diferença não é só sintática.

Ela aparece na responsabilidade:

* não existe encapsulamento real protegendo os dados
* qualquer função pode acessar e modificar tudo
* memória precisa ser gerenciada manualmente

Cada `malloc` precisa de um `free`.
Cada ponteiro precisa estar correto o tempo todo.

Não tem amortecedor.

---

## Um detalhe que eu quis manter

Mesmo sendo C, a organização não ficou largada.

Separei interface e implementação, modularizei o código e evitei misturar lógica de dados com entrada/saída.

Não é algo que a linguagem impõe — é disciplina mesmo.

E faz diferença.

---

## Sobre a “análise” de preços

A parte de decisão é propositalmente simples.

Ela não tenta ser realista nem precisa ser.

Serve mais como uma camada em cima da estrutura, só pra dar sentido ao uso dos dados.

E também deixa o programa menos seco.

---

## O que esse projeto representa

Pra mim, ele é menos sobre comparação de preços e mais sobre contraste:

* em C++, você descreve o que quer
* em C, você precisa garantir que tudo funcione

Mesma ideia, dois níveis diferentes de controle.

---

## Fechamento

Esse tipo de projeto é direto, mas não trivial.

Quando você tira as abstrações, fica mais claro onde estão os problemas de verdade.

E, ao mesmo tempo, mais claro o quanto a organização do código passa a depender de você — não da linguagem.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Price-Comparison-C).

---
