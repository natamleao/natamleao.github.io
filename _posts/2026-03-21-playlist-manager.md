---
layout: post
title: "Playlist Manager"
date: 2026-03-20
categories: portfolio
tags: [C, Data Structures, Algorithms]
image: /assets/images/playlist-manager-thumbnail.png
github: https://github.com/natamleao/Playlist-Manager
excerpt: "Gerenciador de playlists em C usando lista encadeada circular, com funcionalidades completas para manipular músicas e analisar estatísticas."
---

## Visão geral

Este projeto é um **gerenciador de playlists de músicas em C**, construído com foco em **estrutura de dados (lista encadeada circular)** e manipulação manual de memória. O objetivo principal é praticar e demonstrar domínio em conceitos fundamentais da linguagem C por meio de um sistema interativo e completo. 

---

## O que foi construído

O sistema permite:

* Inserir músicas manualmente ou a partir de arquivo;
* Remover músicas da playlist;
* Buscar músicas por nome;
* Ordenar a playlist por duração;
* Salvar playlist em arquivo `.txt`;
* Calcular estatísticas (música mais longa, mais curta, duração total e média);
* Simular execução da playlist em um ciclo infinito. 

Essa lista mostra que o projeto não é só um toy: ele trata dados reais e aplica operações que fazem sentido num sistema de gerenciamento de música. 

---

## Por que esse projeto importa

Esse projeto é um baita exemplo de **prática de C de verdade**. Você lida com:

* Alocação dinâmica de memória (`malloc` e `free`);
* Manipulação de **ponteiros**;
* Estruturação de código em múltiplos arquivos e módulos;
* Separação entre interface (`.h`) e implementação (`.c`);
* Organização de projeto com `Makefile` e diretórios. 

É aquele tipo de projeto que te faz perder medo de ponteiros e entender por que C ainda é essencial na engenharia de software. 

---

## Destaques técnicos

### Estrutura de dados: lista encadeada circular

A playlist é implementada como **lista encadeada circular**, o que facilita operações como navegação contínua e simulação de “reprodução”. Cada nó armazena:

* Nome da música;
* Nome do artista;
* Duração em segundos;
* Ponteiro para o próximo nó. 

---

## Funcionalidades detalhadas

🎵 **Inserção**
Adicionar música ao final da playlist, informando nome, artista e duração — ou carregando de um arquivo `Musics.txt`. 

🔎 **Busca**
Localiza uma música pela string do nome. 

🔄 **Ordenação**
Permite ordenar a playlist por duração total das músicas. 

📊 **Estatísticas**
Calcula diversas métricas úteis sobre a playlist inteira, como duração total e média. 

🛠️ **Execução / Simulação**
Simula a reprodução da playlist em um ciclo circular, repetindo conforme solicitado. 

---

## Estrutura do projeto

```
Playlist-Manager/
├── app/              # Aplicação principal
├── bin/              # Executáveis gerados
├── include/          # Cabeçalhos (.h)
├── obj/              # Objetos compilados
├── src/              # Código-fonte
├── Musics.txt        # Músicas de exemplo
├── My Playlist.txt   # Playlist salva pelo usuário
├── Makefile          # Compilação automatizada
├── README.md         # Documentação
└── LICENSE           # Licença MIT
```

Essa estrutura mostra **organização de projeto madura**, até em C puro. 

---

## Como executar

Para compilar e testar o projeto:

```bash
git clone https://github.com/natamleao/Playlist-Manager.git
cd Playlist-Manager
make
make run
```

Depois de usar, limpe com:

```bash
make clean
make cleanapp
```

Requisitos: **GCC ou Clang (suporte C11)** e **GNU Make** em ambiente **Linux ou macOS**. 

---

## Conclusão

Esse projeto não é só “mais um gerenciador de listas”: ele prova que você sabe lidar com **dados, ponteiros e lógica de software de baixo nível**. Projetos assim vão fazer seu portfólio respirar experiência real em C. 

---

## GitHub

[https://github.com/natamleao/Playlist-Manager](https://github.com/natamleao/Playlist-Manager)

---
