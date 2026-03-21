---
layout: post
title: "Playlist Manager"
date: 2026-03-20
categories: portfolio
mathjax: false
tags: [C, Data Structures, Algorithms]
image: /assets/images/playlist-manager-thumbnail.png
github: https://github.com/natamleao/Playlist-Manager
excerpt: "Gerenciador de playlists em C utilizando lista encadeada circular, com manipulação manual de memória, operações completas e análise de dados."
---

![C](https://img.shields.io/badge/Language-C-blue)
![C11](https://img.shields.io/badge/Standard-C11-orange)
![Makefile](https://img.shields.io/badge/Build-Makefile-green)
![Data Structures](https://img.shields.io/badge/Data_Structures-Linked_List-yellow)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## Visão geral

Este projeto implementa um **gerenciador de playlists em C**, com foco em **estrutura de dados (lista encadeada circular)** e **manipulação manual de memória**.

O objetivo é demonstrar domínio prático dos fundamentos da linguagem C por meio de um sistema completo, modular e interativo, capaz de **armazenar, manipular e analisar dados reais**.

---

## O que foi implementado

O sistema permite:

- Inserir músicas manualmente ou a partir de arquivo  
- Remover músicas da playlist  
- Buscar músicas por nome  
- Ordenar a playlist por duração  
- Salvar playlist em arquivo `.txt`  
- Calcular estatísticas (mais longa, mais curta, duração total e média)  
- Simular execução da playlist em ciclo  

Mais do que um projeto simples, ele aplica operações reais de manipulação e análise de dados.

---

## Estrutura de dados

### Lista encadeada circular

A playlist é implementada como uma **lista encadeada circular**, permitindo navegação contínua — ideal para simular reprodução de músicas.

Cada nó da lista contém:

- Nome da música  
- Nome do artista  
- Duração em segundos  
- Ponteiro para o próximo nó  

Essa estrutura elimina a necessidade de reinicializar a travessia da lista, tornando o modelo mais natural para o domínio do problema.

---

## Modelo de execução

A simulação de reprodução percorre a lista circular continuamente, repetindo conforme o número de ciclos definido pelo usuário.

Esse comportamento reforça o uso prático da estrutura escolhida, conectando teoria e aplicação.

---

## Conceitos aplicados

Este projeto envolve fundamentos essenciais de C:

- Alocação dinâmica de memória (`malloc`, `free`)  
- Manipulação de ponteiros  
- Estruturas de dados encadeadas  
- Separação entre interface (`.h`) e implementação (`.c`)  
- Modularização do código  
- Manipulação de arquivos (`fopen`, `fscanf`, `fprintf`)  
- Organização de projeto com múltiplos diretórios  
- Automação de build com `Makefile`  

---

## Exemplo de entrada (arquivo)

Formato esperado:

```text
Artista;Musica;Duracao
Eminem;Lose Yourself;326
Coldplay;Viva La Vida;242
Adele;Rolling in the Deep;228
````

---

## Pipeline do sistema

O fluxo da aplicação segue:

1. Entrada de dados (manual ou arquivo)
2. Armazenamento em lista encadeada circular
3. Manipulação (inserção, remoção, busca, ordenação)
4. Processamento (estatísticas)
5. Saída (exibição ou persistência em arquivo)

---

## Estrutura do projeto

```text
Playlist-Manager/
│
├── app/              # Aplicação principal
├── bin/              # Executáveis
├── include/          # Cabeçalhos (.h)
├── obj/              # Arquivos objeto
├── src/              # Código-fonte
│
├── Musics.txt        # Dados de entrada
├── My Playlist.txt   # Saída gerada
├── Makefile          # Build
├── README.md         # Documentação
└── LICENSE           # Licença MIT
```

---

## Como executar

```bash
git clone https://github.com/natamleao/Playlist-Manager.git
cd Playlist-Manager
make
make run
```

Para limpar:

```bash
make clean
make cleanapp
```

**Requisitos:** GCC ou Clang (C11) e GNU Make em ambiente Linux/macOS.

---

## Conclusão

Este projeto demonstra domínio sólido de **C em baixo nível**, especialmente no uso de **ponteiros, memória dinâmica e estruturas de dados clássicas**.

Mais importante: ele conecta teoria com prática real, mostrando como uma estrutura como lista encadeada circular pode ser aplicada diretamente em um sistema funcional.

Esse tipo de base é essencial para avançar em áreas como sistemas, engenharia de software e computação de alto desempenho.

---

[Veja o projeto completo no GitHub](https://github.com/natamleao/Playlist-Manager)

---
