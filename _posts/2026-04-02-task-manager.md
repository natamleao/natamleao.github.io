---
layout: post
title: "Gerenciando tarefas e organizando estado em uma aplicação web"
date: 2026-04-02
categories: portfolio
mathjax: false
tags: [JavaScript, Web Development, Persistence]
image: /assets/images/price-comparison-c-thumbnail.png
github: https://github.com/natamleao/Task-Manager
excerpt: "Um gerenciador de tarefas simples para explorar fluxo de dados, persistência e organização em aplicações web."
---

## O ponto de partida

Esse projeto surgiu como uma tentativa de sair do código isolado e entrar em algo mais próximo de uma aplicação de verdade.

A ideia foi simples:

> permitir que dados sejam criados, modificados e mantidos ao longo do tempo

No caso, tarefas.

---

## Interface

<div style="text-align: center;">
  <img src="https://i.imgur.com/FdIszKB.png"
       alt="Página inicial do gerenciador"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

A interface é direta, sem abstrações pesadas.

Isso deixa claro o fluxo completo:  
entrada → processamento → persistência → retorno.

---

## Mais do que CRUD

Na superfície, é um CRUD clássico:

- criar  
- visualizar  
- atualizar  
- remover  

Mas o interessante não é isso.

É o ciclo:

- o usuário interage com a interface  
- os dados são enviados  
- o estado é atualizado  
- a persistência garante que nada se perca  

Mesmo sendo simples, já forma um sistema completo.

---

## Visualização das tarefas

<div style="text-align: center;">
  <img src="https://i.imgur.com/MXCZoEG.png"
       alt="Página de visualização do gerenciador"
       style="display: block; margin: 0 auto; max-width: 100%; width: 100%;">
</div>

Aqui fica mais claro como os dados circulam.

Você cria, altera, remove — e o sistema precisa manter tudo consistente.

---

## Onde as coisas se conectam

Diferente de programas locais, aqui existem camadas:

- interface (HTML/CSS)  
- lógica (JavaScript)  
- servidor  
- banco de dados  

Nada muito complexo isoladamente.

Mas o sistema depende de tudo isso funcionando junto.

---

## Persistência muda o jogo

Usar um banco de dados adiciona um ponto importante:

> os dados deixam de existir só na memória

Eles passam a ter continuidade.

Isso exige:

- consistência nas operações  
- cuidado com atualização e remoção  
- atenção ao fluxo entre cliente e servidor  

---

## Limitações (intencionais)

O projeto não tenta ser um sistema completo.

- sem autenticação  
- backend simples  
- modelo direto  

A ideia não era escalar — era entender o fluxo.

---

## O que esse projeto representa

Ele marca uma transição importante:

de programas isolados  
para aplicações com:

- múltiplas camadas  
- estado persistente  
- interação contínua  

---

## Fechamento

No fim, o sistema é simples.

Mas já exige algo além de código que “funciona”:

> exige manter consistência ao longo do tempo

E isso muda completamente o tipo de problema.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Task-Manager).

---
