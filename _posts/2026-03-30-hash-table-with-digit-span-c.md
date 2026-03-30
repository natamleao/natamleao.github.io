---
layout: post
title: "Hash Table com Análise de Dígitos em C"
date: 2026-03-30
categories: portfolio
mathjax: false
tags: [C, Data Structures, Hash Table]
image: /assets/images/umbrellan.png
github: https://github.com/natamleao/Hash-Table
excerpt: "Implementação de tabela hash em C com estratégia adaptativa baseada em análise de dígitos para melhoria de distribuição."
---

![C](https://img.shields.io/badge/language-C-blue)
![C11](https://img.shields.io/badge/standard-C11-orange)
![Makefile](https://img.shields.io/badge/build-Makefile-green)
![Hash Table](https://img.shields.io/badge/data_structure-hash_table-yellow)
![Chaining](https://img.shields.io/badge/collision-chaining-lightgrey)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## Visão geral

Este projeto implementa uma **tabela hash em C (C11)** utilizando **encadeamento (chaining)** para resolução de colisões.

O diferencial está na estratégia de hashing: ao invés de usar uma função fixa, o sistema realiza uma **análise dos dígitos das chaves** para selecionar dinamicamente a melhor forma de distribuição.

A proposta é simples, mas poderosa: **usar informação estatística dos dados de entrada para influenciar o hashing**.

---

## O que foi implementado

O sistema oferece:

- Criação de tabela hash com capacidade definida  
- Inserção baseada em análise global dos dados  
- Tratamento de colisões via lista encadeada  
- Impressão completa da estrutura  
- Liberação segura de memória  
- Geração de dados aleatórios sem repetição para testes  

---

## Estratégia de hashing (núcleo do projeto)

O índice não é calculado diretamente a partir da chave. Em vez disso, o sistema executa um pipeline:

1. **Decomposição em dígitos**  
   Cada número é transformado em um vetor de dígitos  

2. **Matriz de distribuição**  
   Conta a frequência de cada dígito (0–9) em cada posição  

3. **Cálculo de desvio**  
   Mede o quão distante cada posição está de uma distribuição ideal  

4. **Seleção da melhor posição**  
   Escolhe o dígito mais estável (menor desvio)  

5. **Cálculo do índice**  

```c
   index = digit % capacity;
````

👉 Resultado: o hashing passa a ser **adaptativo ao conjunto de dados**, não fixo.

---

## Estrutura de dados

### Tabela hash com encadeamento

Cada bucket aponta para uma lista encadeada:

```
[0] → (k,v) → (k,v)
[1] → vazio
[2] → (k,v)
[3] → (k,v) → (k,v)
```

---

### Estrutura do nó

```c
struct _node{
    int _index;
    int _value;
    struct _node *_next;
};
```

* `_index`: posição na tabela (bucket)
* `_value`: valor original inserido
* `_next`: próximo elemento da lista

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

O módulo `keyarray` gera conjuntos de teste:

```c
KeyArrayCreate(qtd, min, max);
```

Características:

* Valores únicos
* Distribuição aleatória (Fisher-Yates shuffle)
* Ideal para validar distribuição da hash

---

## Conceitos aplicados

Esse projeto trabalha fundamentos importantes:

* Alocação dinâmica (`malloc`, `calloc`, `free`)
* Ponteiros e manipulação de memória
* Listas encadeadas
* Modularização em C (`.h` / `.c`)
* Separação de responsabilidades
* Análise de distribuição de dados
* Uso de função como parâmetro (callback)
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

Limpeza:

```bash
make clean
make cleanapp
```

**Requisitos:** GCC ou Clang + GNU Make (Linux/macOS)

---

## Limitações e observações

* O método depende da distribuição dos dados de entrada
* Não há redimensionamento dinâmico da tabela
* Não implementa busca ou remoção
* O cálculo de desvio é heurístico, não probabilístico rigoroso

Em outras palavras: é uma abordagem **experimental e exploratória**, não uma hash universal.

---

## Conclusão

O projeto explora uma alternativa simples para o problema de distribuição em tabelas hash, utilizando informações do próprio conjunto de dados.

---

[Veja o projeto completo no GitHub](https://github.com/natamleao/Hash-Table)

---
