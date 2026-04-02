---
layout: post
title: "Gerenciando alunos e persistindo dados"
date: 2026-03-24
categories: portfolio
mathjax: false
tags: [C, Data Structures]
image: /assets/images/student-management-c-thumbnail.png
github: https://github.com/natamleao/Student-Management-System
excerpt: "Sistema em C com lista duplamente encadeada e persistência em arquivo binário."
---

## Um passo além da memória

Esse projeto nasceu de uma mudança simples de foco.

Até então, os programas começavam, rodavam e acabavam — tudo existia só durante a execução.

Aqui a ideia foi outra:

> manter dados vivos mesmo depois do programa terminar

Isso muda bastante o tipo de problema.

---

## Não é só armazenar — é manter consistência

Gerenciar alunos, por si só, não é complicado:

* cadastrar
* remover
* buscar
* listar

Mas quando você adiciona persistência, entra outra camada:

* o que está em memória precisa refletir o que está em disco
* leitura e escrita precisam ser compatíveis
* qualquer inconsistência quebra tudo silenciosamente

Deixa de ser só manipulação de dados — vira manutenção de estado.

---

## A escolha da estrutura

Usei uma **lista duplamente encadeada**.

Aqui a escolha foi bem intencional.

Ela não é a mais simples, mas resolve bem algumas operações:

* remoção sem precisar percorrer desde o início
* navegação nos dois sentidos
* inserções mais flexíveis

Para um sistema que sofre alterações frequentes, isso ajuda a manter o comportamento previsível.

---

## Onde o projeto realmente começa

A parte mais interessante não foi a lista.

Foi a persistência em **arquivo binário**.

Em vez de serializar para texto, a ideia foi trabalhar direto com bytes.

Isso exige mais cuidado:

* definir exatamente o que é escrito
* garantir que a leitura reconstrua corretamente
* lidar com tamanhos variáveis (principalmente strings)

Nada disso é difícil isoladamente — mas tudo precisa bater exatamente.

---

## Um detalhe que faz diferença

Strings não são triviais aqui.

Salvar um inteiro é direto.
Salvar uma string exige:

* armazenar o tamanho
* escrever o conteúdo
* reconstruir corretamente depois

Se qualquer parte disso falhar, o dado corrompe.

E não tem aviso.

---

## Quando as coisas começam a se conectar

Esse projeto junta várias camadas que isoladamente são simples:

* memória dinâmica
* estruturas encadeadas
* manipulação de arquivos

Mas juntas, elas exigem mais rigor.

Você precisa garantir:

* alocação correta
* liberação correta
* cópia correta
* leitura e escrita coerentes

Não dá pra “deixar passar”.

---

## O que esse projeto representa

Ele fica num ponto interessante entre exercício e sistema real.

Não é complexo, mas já força a pensar em:

* persistência
* consistência
* organização de dados

Coisas que não aparecem quando tudo vive só em memória.

---

## Fechamento

A principal diferença aqui não está no algoritmo nem na estrutura.

Está no fato de que os dados continuam existindo depois.

E isso muda o tipo de cuidado que o código exige.

Quando você passa a lidar com estado persistente, pequenos erros deixam de ser locais — eles se acumulam.

E é aí que o nível do problema sobe.

---

## Código

Você pode encontrar o projeto completo [aqui](https://github.com/natamleao/Student-Management-System).

---
