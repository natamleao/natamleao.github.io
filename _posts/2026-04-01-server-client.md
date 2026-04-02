---
layout: post
title: "Servidor de comunicação e o problema de lidar com múltiplos clientes"
date: 2026-04-01
categories: portfolio
mathjax: false
tags: [Python, Networking, Systems]
image: /assets/images/umbrellan.png
github: https://github.com/natamleao/Server-Client
excerpt: "Um servidor em Python baseado em sockets TCP que lida com múltiplos clientes e organiza diferentes tipos de requisição."
---

## O ponto de partida

Esse projeto começou com uma ideia simples:

> fazer dois programas conversarem

Mas rapidamente isso evolui.

Porque no momento em que você sai de um cliente único e entra em múltiplos clientes, o problema muda completamente.

---

## Não é só conexão

Abrir um socket e trocar dados é direto.

O problema real começa quando você precisa lidar com:

* múltiplas conexões ao mesmo tempo
* diferentes tipos de requisição
* respostas consistentes para cada cliente

Aqui já não é mais só comunicação — é organização.

---

## Um servidor, várias responsabilidades

O servidor centraliza tudo.

Ele precisa:

* aceitar conexões
* interpretar o que o cliente quer
* decidir qual funcionalidade executar
* responder corretamente

E tudo isso sem “misturar” os clientes.

---

## Tipos de interação

As funcionalidades em si são simples, mas ajudam a exercitar diferentes cenários:

* responder informações (curiosidades)
* gerar dados em tempo real (hora do servidor)
* enviar arquivos
* listar conteúdo disponível

Cada uma dessas ações exige um tipo diferente de tratamento.

---

## Onde começa a complicar

Quando vários clientes entram ao mesmo tempo, aparecem questões que não existem em programas locais:

* concorrência
* ordem de execução
* consistência das respostas
* tratamento de erro em rede

Nada disso aparece se você testa com um único cliente.

---

## Um detalhe importante

A comunicação aqui não é só envio de dados.

Existe um “protocolo implícito”:

> o cliente precisa saber o que pode pedir
> o servidor precisa entender o que foi pedido

Mesmo que simples, isso já é uma forma de contrato.

---

## O que esse projeto mostra

Ele não tenta ser um servidor completo.

Mas já mostra bem a transição de:

* execução local
* para comunicação entre processos
* para sistemas com múltiplos pontos interagindo

E isso muda completamente o tipo de problema.

---

## Limitações

Algumas coisas ficaram de fora — propositalmente:

* autenticação
* criptografia
* controle mais sofisticado de concorrência

A ideia aqui não foi robustez total, e sim entender o funcionamento.

---

## Fechamento

No fim, o projeto começa simples — abrir conexão, trocar dados.

Mas rapidamente revela algo maior:

> quando múltiplos agentes começam a interagir, organizar a comunicação passa a ser o problema central

E isso já é o começo de pensar em sistemas distribuídos.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Server-Client).

---
