---
title: "Simulação de movimento com integração numérica"
date: 2026-03-18
layout: post
categories: portfolio
mathjax: true
excerpt: "Implementação de uma simulação física usando método de Euler para modelar movimento."
---

## Visão geral

Neste projeto, implementei uma simulação simples de movimento usando integração numérica.

Objetivo:

- modelar posição e velocidade ao longo do tempo  
- entender na prática equações diferenciais  

---

## Modelo físico

Parti da equação básica:

$$ F = m a $$

Reescrevendo:

$$ a = \frac{F}{m} $$

E usando:

$$ v = \frac{dx}{dt} $$

---

## Aproximação numérica (Euler)

Como não dá pra resolver analiticamente sempre, usei:

$$ v_{n+1} = v_n + a \cdot \Delta t $$  
$$ x_{n+1} = x_n + v_n \cdot \Delta t $$  

👉 Isso transforma equações contínuas em passos discretos.

---

## Implementação em C

```c
#include <stdio.h>

int main() {
    double x = 0.0;
    double v = 0.0;
    double a = 9.8;
    double dt = 0.01;

    for (int i = 0; i < 1000; i++) {
        v = v + a * dt;
        x = x + v * dt;

        printf("t=%.2f x=%.2f v=%.2f\n", i*dt, x, v);
    }

    return 0;
}
