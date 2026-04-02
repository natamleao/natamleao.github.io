---
layout: post
title: "Gerenciando playlists com lista encadeada circular"
date: 2026-03-20
categories: portfolio
mathjax: false
tags: [C, Data Structures]
image: /assets/images/playlist-manager-thumbnail.png
github: https://github.com/natamleao/Playlist-Manager
excerpt: "Gerenciador de playlists em C utilizando lista encadeada circular e manipulação manual de memória."
---

## Por que uma *playlist*?

Esse projeto começou com uma ideia simples: pegar algo cotidiano — uma *playlist* — e modelar isso direito em C.

Não só armazenar músicas, mas representar o comportamento real. Aquele fluxo contínuo onde uma música leva à próxima, e a última naturalmente volta pra primeira, sem “fim” explícito.

Isso me interessou mais do que o problema em si.

---

## A escolha da estrutura 

A decisão por uma **lista encadeada circular** veio quase como consequência.

Não foi “vou usar isso porque é interessante”, mas sim:
isso resolve o comportamento da forma mais direta possível.

Sem precisar ficar tratando exceções o tempo todo, tipo “chegou no final da lista”. Simplesmente não existe final — só continuidade.

Esse tipo de encaixe entre problema e estrutura é o tipo de coisa que eu acho elegante.

---

## Onde o detalhe começa a importar

Claro, essa escolha traz algumas responsabilidades.

Nada absurdo, mas o suficiente pra não dar pra escrever no automático:

* remover um elemento muda dependendo do contexto da lista
* o ponteiro inicial precisa ser tratado com cuidado
* percorrer a lista exige saber exatamente quando parar

São aquelas situações em que o código não é complexo, mas também não tolera descuido.

---

## Construindo em cima disso

Com a base bem definida, o resto do projeto foi se organizando sem muita fricção:

* adicionar e remover músicas
* ordenar por duração
* buscar elementos
* carregar e salvar em arquivo
* calcular estatísticas
* simular a execução da *playlist*

Nada aqui é particularmente sofisticado isoladamente. O ponto é que tudo se apoia na mesma estrutura e segue a mesma lógica.

---

## Um detalhe que eu valorizo

Uma coisa que fiz questão foi manter o código organizado:

separar interface de implementação, evitar misturar lógica de dados com entrada/saída, deixar o módulo da *playlist* relativamente independente.

Não é nada revolucionário, mas é o tipo de cuidado que evita bagunça quando o projeto cresce.

---

## No fim

Esse projeto não é sobre complexidade.

É sobre pegar uma ideia simples e modelar direito, sem forçar solução.

Pra mim, o mais interessante aqui foi justamente isso:
quando a estrutura encaixa bem, o resto deixa de ser problema e vira consequência.

E esse tipo de ajuste fino — entre problema e representação — é o tipo de coisa que eu gosto de perseguir.


---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Playlist-Manager).

---
