---
layout: post
title: "Gerenciando playlists com lista encadeada circular em C"
date: 2026-03-20
categories: portfolio
mathjax: false
tags: [C, Data Structures]
image: /assets/images/playlist-manager-thumbnail.png
github: https://github.com/natamleao/Playlist-Manager
excerpt: "Gerenciador de playlists em C utilizando lista encadeada circular e manipulação manual de memória."
---

## Um problema simples, tratado com a estrutura certa

Esse projeto nasce de uma ideia direta: representar uma *playlist* de forma fiel ao seu comportamento.

Não como uma lista estática de elementos, mas como algo que **continua indefinidamente**. Uma sequência que não tem “último” no sentido prático — apenas um ponto de retorno.

Isso levou naturalmente à escolha de uma **lista encadeada circular**.

---

## Modelar comportamento, não só armazenar dados

A estrutura resolve bem mais do que armazenamento.

Ela define como a *playlist* se comporta:

* a navegação nunca termina
* não existe estado “fora da lista”
* a transição entre músicas é contínua

Isso evita tratamentos artificiais, como verificar fim de lista a todo momento. O próprio modelo elimina essa preocupação.

---

## Decisões que importam

Trabalhar com lista circular não é complicado — mas exige consistência.

Operações simples em outras estruturas passam a ter mais impacto aqui:

* remoção precisa preservar o ciclo
* inserção precisa manter a integridade da referência inicial
* percorrer a lista exige critério claro de parada

Nada disso é “difícil”, mas tudo exige atenção. Pequenos descuidos quebram a estrutura de forma silenciosa.

---

## Organização acima de tudo

Um ponto importante desse projeto foi manter o código bem separado:

* interface em `.h`
* implementação em `.c`
* responsabilidades bem definidas

Isso permite que a estrutura de dados não fique misturada.

Na prática, a *playlist* vira um módulo reutilizável, não só um bloco de código acoplado ao `main`.

---

## Funcionalidade como consequência

As funcionalidades surgem quase naturalmente a partir da base:

* inserção e remoção de músicas
* ordenação por duração
* busca
* cálculo de estatísticas
* leitura e escrita em arquivos
* simulação de execução da playlist

Nada disso exige soluções exóticas — o ponto é que tudo se apoia na mesma estrutura consistente.

---

## O que vale destacar aqui

Esse não é um projeto sobre “fazer muitas coisas”.

É sobre fazer uma escolha estrutural adequada e deixar o resto se organizar em cima disso.

A lista encadeada circular não foi usada por ser “diferente”, mas porque encaixa bem no problema.

E quando a estrutura encaixa, o código tende a ficar mais direto, sem tratamentos desnecessários.

---

## Fechamento

No fim, esse projeto é menos sobre playlists e mais sobre representação.

Sobre escolher uma estrutura que respeite o comportamento do problema desde o início — e evitar remendos depois.

É um exercício simples na superfície, mas que reforça uma ideia que aparece o tempo todo:

> boas decisões estruturais economizam complexidade lá na frente.

---

## Código

O projeto completo está disponível no [GitHub](https://github.com/natamleao/Playlist-Manager).

---
