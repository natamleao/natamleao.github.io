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

Queria construir algo um pouco mais próximo de um uso real.

Uma playlist é um bom exemplo:  
- tem sequência  
- pode crescer e diminuir  
- e, principalmente, não “termina” — ela volta pro início  

Isso encaixa bem com uma **lista encadeada circular**.

---

## O que foi feito

Implementei um gerenciador de playlists em C que permite:

- adicionar músicas  
- remover e buscar  
- ordenar por duração  
- salvar e carregar de arquivo  
- calcular estatísticas  
- simular reprodução em ciclo  

Tudo rodando em linha de comando, com controle manual de memória.

---

## Estrutura escolhida

Usei uma lista encadeada circular.

A principal vantagem aqui é simples:

> não existe “fim” da playlist

Quando chega no último elemento, ela naturalmente volta para o primeiro.  
Isso deixa a simulação de reprodução muito mais direta.

---

## Um detalhe interessante

A escolha da estrutura muda completamente a forma de percorrer os dados.

Em uma lista comum, você precisa tratar fim da lista.  
Aqui, o cuidado é outro:

- evitar loops infinitos  
- definir bem o ponto de parada  

Parece detalhe pequeno, mas muda a lógica.

---

## Entrada e saída

O sistema também lê e escreve arquivos `.txt`, usando um formato simples:

```text
Artista;Musica;Duracao
```

Isso permite testar com dados maiores sem depender de entrada manual.

---

## Por que esse projeto

A ideia aqui foi:

- aplicar estrutura de dados em um contexto mais “real”  
- trabalhar com arquivos junto com memória dinâmica  
- lidar com um fluxo contínuo (circular) de dados  

---

## Observações

- toda a memória é gerenciada manualmente  
- a ordenação é feita sobre a própria lista  
- a simulação de execução depende da natureza circular da estrutura  

---
 
## Código

O projeto completo está disponível [aqui](https://github.com/natamleao/Playlist-Manager).

---
