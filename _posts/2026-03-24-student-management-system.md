---
layout: post
title: "Student Management System"
date: 2026-03-24
categories: portfolio
mathjax: false
tags: [C, Data Structures, Systems Programming]
image: /assets/images/student-management-c-thumbnail.png
github: https://github.com/natamleao/Student-Management-System
excerpt: "Sistema em C para gerenciamento de alunos utilizando lista duplamente encadeada e persistência em arquivo binário."
---

![C](https://img.shields.io/badge/Language-C-blue)
![C11](https://img.shields.io/badge/Standard-C11-orange)
![Makefile](https://img.shields.io/badge/Build-Makefile-green)
![Data Structures](https://img.shields.io/badge/Data_Structures-Doubly_Linked_List-yellow)
![Binary](https://img.shields.io/badge/Storage-Binary_File-purple)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## Visão geral

Este projeto implementa um sistema em **C (C11)** para **gerenciamento de alunos**, utilizando uma **lista duplamente encadeada** como estrutura principal e **persistência em arquivo binário**.

O foco é trabalhar diretamente com conceitos fundamentais da linguagem, como **gerenciamento manual de memória**, manipulação de ponteiros e controle explícito da estrutura dos dados.

---

## O que foi implementado

O sistema permite:

- Cadastrar alunos com dados completos  
- Remover registros da lista  
- Buscar alunos por matrícula  
- Listar todos os alunos cadastrados  
- Exibir quantidade total de registros  
- Salvar e carregar dados automaticamente em arquivo binário  

Cada aluno possui um **livro favorito**, adicionando um nível extra de composição de estruturas.

---

## Estrutura de dados

### Lista duplamente encadeada

A estrutura principal mantém ponteiros para o **início e o fim da lista**, permitindo operações eficientes:

- Inserção em O(1) nas extremidades  
- Remoção eficiente  
- Navegação bidirecional  

Cada nó contém:

- Nome do aluno  
- Matrícula  
- Idade  
- Livro favorito  
- Ponteiros para anterior e próximo  

---

## Persistência em arquivo binário

Diferente de abordagens baseadas em texto, este projeto implementa **serialização manual em binário**.

Os dados são armazenados como sequência de bytes, seguindo um formato definido pelo programa:

- Tamanho da string + conteúdo  
- Dados numéricos diretamente em memória  
- Estruturas compostas reconstruídas na leitura  

Essa abordagem elimina parsing e aumenta desempenho, ao custo de maior controle manual.

---

## Pipeline do sistema

O fluxo da aplicação segue:

1. Entrada de dados via CLI  
2. Armazenamento em lista encadeada  
3. Manipulação (inserção, remoção, busca)  
4. Serialização para arquivo binário  
5. Desserialização ao iniciar o programa  

---

## Conceitos aplicados

Este projeto reforça conceitos essenciais de programação em C:

- Alocação dinâmica (`malloc`, `free`)  
- Gerenciamento manual de memória  
- Deep copy de estruturas (`strdup`)  
- Manipulação de ponteiros  
- Estruturas encadeadas (lista duplamente encadeada)  
- Serialização e desserialização de dados  
- Separação entre interface (`.h`) e implementação (`.c`)  
- Modularização do código  
- Organização de projeto em múltiplos diretórios  
- Automação de build com `Makefile`  

---

## Estrutura do projeto

```text
Student-Management-System/
│
├── app/            # Aplicação principal
├── src/            # Implementação
├── include/        # Interfaces
├── obj/            # Arquivos objeto
├── bin/            # Executável
├── data/           # Arquivo binário (.bin)
│
├── Makefile        # Build
├── README.md       # Documentação
└── LICENSE         # Licença MIT
````

---

## Como executar

```bash
git clone git@github.com:natamleao/Student-Management-System.git
cd Student-Management-System
make
make run
```

Para limpar:

```bash
make clean
make cleanapp
```

**Requisitos:** GCC ou Clang com suporte a C11 e GNU Make em ambiente Linux/macOS.

---

## Conclusão

Este projeto aprofunda o uso de C em um nível mais próximo de sistemas reais, onde o programador é responsável por **memória, estrutura e persistência dos dados**.

Ao implementar manualmente estruturas dinâmicas e serialização binária, o código deixa de ser apenas um exercício acadêmico e passa a refletir práticas fundamentais de **programação de sistemas**.

---

[Veja o projeto completo no GitHub](https://github.com/natamleao/Student-Management-System)

---
