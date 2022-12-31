---
layout: post
title:  "[Conceito] - Relógios Monotônicos"
date:   2022-11-13
categories: conceitos
tags: conceito
---

> Conteúdo original em [https://twitter.com/zanfranceschi/status/1591969680582844417](https://twitter.com/zanfranceschi/status/1591969680582844417)

---

Ei dev,

Hoje é domingo a noite e tá meio monótono aqui pra mim. Aliás, vamos falar de monotonia? Mais especificamente de relógio monotônico.

cc @sseraphini

↓

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0092t2hun4p7h84kxcdh.png)

---

A definição de um relógio monotônico é um relógio que sempre vai pra frente, nunca pra trás. Ele não funciona como um relógio para saber as horas ─ funciona como um cronômetro.

"Hein? Relógios que vão pra trás?!". Estranho, né? Te explico.

---

Para os relógios "normais", computadores possuem um oscilador de cristal que mantém uma frequência bem precisa pra deixar um relógio no tempo correto. Mas esse mecanismo não é perfeito e o tempo vai variando e fazendo com que os relógios se desregulem às vezes.

---

Pra minimizar essa imprecisão, existe o protocolo NTP (Network Time Protocol) que é usado pra ajustar os relógios dos computadores, por exemplo.

Por causa desses ajustes, a gente pode considerar que os relógios podem (e vão) voltar no passado ou dar saltos pro futuro.

---

Esse é um dos motivos de você já ter ouvido pra não usar esse relógio "normal" para cronometrar tempos de processamento.

Esse é um exemplo de código com uma medição que pode ser bem imprecisa porque pode ocorrer um ajuste do relógio no meio da execução da função cronometrada.

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lanwt4b78vts3jqxrlkk.png)

---

Uma forma mais precisa de medir o tempo de processamento seria usar um relógio monotônico.

O exemplo aqui usa uma função do Python que oferece esse tipo de relógio (cronômetro). Aqui, não existe o risco de saltos de tempo e a medição é bem precisa.

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fqglkhqbab4jpr5eeyuj.png)

---

Relógios, timestamps, etc. são super complexos na verdade, principalmente em sistemas distribuídos. Imagina regular um relógio via NTP numa rede com latência variável, congestionamento, etc.

Imagina ainda ordenar eventos de máquinas diferentes com base em timestamps ─ loucura!

---

Bem, era isso que tinha pra falar sobre relógios monotônicos e não monotônicos ─ espero que tenha gostado.

Obrigado por ter lido até aqui e pela moral! 💕

