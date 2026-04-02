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

## Ideia

A proposta foi construir algo mais próximo de um uso real.

Uma *playlist* é um ótimo exemplo:

- possui uma sequência de elementos  
- cresce e diminui dinamicamente  
- e, principalmente, não possui um fim — ela retorna ao início  

Esse comportamento encaixa perfeitamente com uma **lista encadeada circular**.

---

## Funcionalidades

O sistema implementado permite:

- adicionar músicas (*input manual* ou via arquivo)
- remover e buscar músicas
- ordenar por duração
- salvar e carregar dados em arquivos `.txt`
- calcular estatísticas
- simular reprodução contínua (*loop*)

Tudo isso em ambiente de linha de comando, com **controle manual de memória**.

---

## Estrutura de dados

A estrutura central do projeto é uma **lista encadeada circular**.

A principal vantagem é direta:

> não existe “fim” da *playlist*

Ao chegar no último elemento, a execução retorna automaticamente ao primeiro, o que simplifica bastante a lógica de reprodução contínua.

Por outro lado, isso traz novos cuidados:

- evitar *loops* infinitos
- definir corretamente o ponto de parada nas iterações

Esse detalhe muda completamente a forma de percorrer os dados em relação a listas lineares.

---

## Entrada e saída

O sistema suporta leitura e escrita em arquivos `.txt`, utilizando um formato simples:

```text
Artista;Musica;Duracao
````

Exemplo:

```text
Eminem;Lose Yourself;326
Coldplay;Viva La Vida;242
Adele;Rolling in the Deep;228
```

Isso permite testar o sistema com volumes maiores de dados sem depender de entrada manual.

---

## Objetivo

O foco do projeto foi:

* aplicar estruturas de dados em um contexto mais realista
* trabalhar com **memória dinâmica e arquivos simultaneamente**
* lidar com fluxo contínuo de dados usando uma estrutura circular

---

## Observações técnicas

* toda a memória é gerenciada manualmente (`malloc` / `free`)
* a ordenação é feita diretamente sobre a lista encadeada
* a simulação de execução explora a natureza circular da estrutura

---

## Código

O projeto completo está disponível no [GitHub](https://github.com/natamleao/Playlist-Manager).

---
