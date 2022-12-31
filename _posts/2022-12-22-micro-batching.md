---
layout: post
title:  "[Conceito/Desafio] - Micro-Batching ou Processamento em Micro-Lotes"
date:   2022-12-22
categories: conceitos
tags: desafio conceito
---

> Conteúdo original em [https://twitter.com/zanfranceschi/status/1605916558433193984](https://twitter.com/zanfranceschi/status/1605916558433193984)

---

Ei dev,

Já ouviu falar sobre MICRO-BATCHING (processamento em micro-lotes)? Se ainda não, cola mais pra você levar esse assunto pra ceia de Natal e impressionar a família!

Tem até um desafio no final. 🥲

cc @sseraphini

↓

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/k81uleio1jpmlsdeokyv.png)

---

Antes de explicar micro-batching, precisamos entender dois conceitos:

- Processamento batch (em lote)

- Processamento contínuo

---

Processamento em lote ou batch significa processar múltiplos registros de uma só vez. Antigamente, havia muitas restrições para comunicação entre computadores. Então, basicamente o pessoal juntava um bolo de informações e mandava processar numa tacada só.

---

Já o processamento contínuo é uma técnica que processa dados assim que estiverem disponíveis ─ muito usada em arquiteturas orientadas a eventos. Filas e tópicos (no caso do Kafka) são ferramentas bem comuns pra isso. O dado pintou lá, pá! Já processa na hora, no ato!

---

Bom, agora sobre micro-batching. Nada mais é do que um processamento de lotes bem menores e com intervalos também bem menores do que os tradicionais batches.

É justo interpretar micro-batching como um meio termo entre/mistura de processamento contínuo e em lote.

---

O intervalo de processamento e o tamanho do lote podem variar de acordo com a natureza do problema. Inclusive, tamanho e/ou intervalo geralmente são os gatilhos para que se inicie o processamento:

- Processar de tanto em tanto tempo;
- Processar a cada X volume de dados.

---

Pra usar micro-batching você precisa considerar principalmente o quão tardiamente seus dados podem ser processados (segundos, horas?) e a eficiência computacional do processamento pra tal tamanho/intervalo (custos, uso de rede, etc.). Dependendo do cenário, pode não valer a pena.

---

Alguns cenários que PODEM se beneficiar dessa técnica:

- Ferramentas de analytics;
- Ingestão/sincronização de bases;
- IoT;
- Processamento entre processos;
- Etc.

---

Bom, agora que você já deve ter pelo menos uma intuição sobre o assunto, talvez valha a pena implementar esse desenho como desafio/prática.

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/cyijntkh9iqzwubxkkx2.png)

---

Era isso que tinha pra falar sobre micro-batching. Como sempre, muito obrigado por ter lido até aqui! ♥️

Se curtiu, dá um like, retuíta o primeiro tweet da thread, comenta, compartilha, etc.
