---
layout: post
title: "Hash Table com Análise de Dígitos em C"
date: 2026-03-30
categories: portfolio
mathjax: false
tags: [C, Data Structures, Hash Table]
image: /assets/images/hash-table-thumbnail.png
github: https://github.com/natamleao/Hash-Table
excerpt: "Implementação de tabela hash em C com estratégia de distribuição baseada em análise de dígitos para redução de colisões."
---

![C](https://img.shields.io/badge/language-C-blue)
![C11](https://img.shields.io/badge/standard-C11-orange)
![Makefile](https://img.shields.io/badge/build-Makefile-green)
![Hash Table](https://img.shields.io/badge/data_structure-hash_table-yellow)
![Chaining](https://img.shields.io/badge/collision-chaining-lightgrey)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## Visão geral

Este projeto implementa uma **tabela hash em C (C11)** utilizando **encadeamento (chaining)** para tratamento de colisões.

O diferencial está na estratégia de hashing: em vez de aplicar uma função fixa, o sistema realiza uma **análise dos dígitos das chaves** para escolher a melhor forma de distribuição.

A proposta é reduzir colisões utilizando uma abordagem baseada em **heurística e distribuição estatística simples**.

---

## O que foi implementado

O sistema permite:

- Criação de tabela hash com capacidade definida  
- Inserção de elementos com distribuição otimizada  
- Tratamento de colisões via lista encadeada  
- Impressão da estrutura completa  
- Liberação correta de memória  

Além disso, inclui um módulo para geração de dados de teste.

---

## Estratégia de hashing

A construção do índice segue um pipeline:

1. Decomposição dos números em dígitos  
2. Construção de matriz de distribuição  
3. Cálculo de desvio em relação a uma distribuição ideal  
4. Seleção do dígito mais equilibrado  
5. Cálculo do índice com base nesse dígito  

Essa abordagem busca melhorar a uniformidade da hash de forma adaptativa.

---

## Estrutura de dados

### Tabela hash com encadeamento

Cada bucket da tabela aponta para uma lista encadeada:

```

[0] → (k,v) → (k,v)
[1] → vazio
[2] → (k,v)
[3] → (k,v) → (k,v)

````

---

### Estrutura do nó

```c
struct _node{
    int _index;
    int _value;
    struct _node *_next;
};
````

---

### Estrutura da tabela

```c
struct _hashTable{
    Node **buckets;
    int size;
    int capacity;
};
```

---

## Geração de dados

O módulo `keyarray` permite gerar conjuntos de chaves únicas:

```c
KeyArrayCreate(qtd, min, max);
```

Características:

* Sem repetição
* Distribuição aleatória
* Ideal para testes da hash

---

## Conceitos aplicados

Este projeto reforça conceitos fundamentais de C:

* Alocação dinâmica (`malloc`, `calloc`, `free`)
* Manipulação de ponteiros
* Estruturas encadeadas
* Modularização com `.h` e `.c`
* Separação entre interface e implementação
* Análise de distribuição de dados
* Uso de funções como ponteiros (callback)
* Algoritmos de embaralhamento

---

## Estrutura do projeto

```text
Hash-Table/
│
├── app/             # Aplicação principal (main)
├── bin/             # Executáveis
├── include/         # Headers (.h)
├── build/           # Arquivos objeto (.o)
├── src/             # Código-fonte (.c)
├── lib/             # Biblioteca estática
│
├── Makefile         # Regras de compilação
├── README.md        # Documentação do projeto
└── LICENSE          # Licença do projeto
```

---

## Como executar

```bash
git clone https://github.com/natamleao/Hash-Table.git
cd Hash-Table
make
make run
```

Para limpar:

```bash
make clean
make cleanapp
```

**Requisitos:** GCC ou Clang e GNU Make em ambiente Linux/macOS.

---

## Conclusão

Este projeto vai além de uma implementação tradicional de tabela hash ao introduzir uma estratégia baseada em **análise de distribuição de dados**.

Ele demonstra não apenas domínio de estruturas clássicas, mas também capacidade de explorar abordagens alternativas para melhorar eficiência — um passo importante na direção de projetos mais avançados em algoritmos e sistemas.

---

[Veja o projeto completo no GitHub](https://github.com/natamleao/Hash-Table)

---
