---
layout: post
title:  "[Desafio] - Desenhar uma Solução de Lançamentos Financeiros a Partir de Requisitos"
date:   2022-12-11
categories: desafios
tags: desafio
---

> Conteúdo original em [https://twitter.com/zanfranceschi/status/1601954872168837120](https://twitter.com/zanfranceschi/status/1601954872168837120)

---

Ei dev, achou que minhas threads tinham ido de base, né? 🤭

Pra você que cansou de fazer CRUD e tá sem inspiração pra estudar/praticar, vou propor um desafio em que só descrevo os requisitos e restrições sobre um assunto conhecido – lançamentos financeiros.

cc @sseraphini

↓

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0u1pzswnlroa6cgx8q3g.png)

---

Esse tipo de situação é comum pra quem trabalha com desenvolvimento. O cliente quer uma aplicação, fala como algumas coisas têm que ser e deixa outras em aberto. É um cenário realista e legal pra quem gosta de arquitetura e/ou quer alguma coisa diferente pra praticar.

---

DISCLAIMER

Esse é um desafio um pouco mais avançando. Então se vc for iniciante não se preocupe caso não entenda alguma coisa. Se quiser mesmo assim fazer e tiver alguma dúvida, é só perguntar aqui! Só gente legal lê minhas threads e alguém vai te ajudar! 💕

---

Vamos então começar com o que a nossa solução deverá entregar. É basicamente uma API mais ou menos como mostra a imagem.

São dois endpoints, um para o saldo atual e outro para mostrar os lançamentos.

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vo96ix16m05kmu8clbqg.png)

---

Bora pros requisitos.

\- Essa API deve ser otimizada pra leitura. Ela deve apenas ler o saldo pronto de um banco de dados sem precisar computá-lo a cada leitura.

\- Ela tem que limitar a leitura dos lançamentos – uma paginação e filtros por período são necessários.

---

\- Apenas lançamentos de até 90 dias ficam disponíveis no endpoint de lançamentos – nada antes disso.

\- Para lançamentos anteriores a 90 dias, tem que haver um endpoint para fazer a solicitação e então a aplicação gerar um arquivo para ficar disponível pra download. +

---

Então, na verdade, precisamos de mais alguns endpoints: solicitação de lançamentos anteriores a 90 dias; consulta dessas solicitações; e download desses lançamentos antigos. Ah, tem que haver um expurgo desses arquivos também.  (Esteja preparada/o para solicitações de mudanças!)

---

\- Para alimentar o banco da API, os lançamentos são disponibilizados de duas formas:

1- Um arquivo gerado diariamente; e

2- Uma fila onde, em tempo quase real, os lançamentos são publicados.

Aqui, a abordagem com filas é mais desejada do que a leitura de arquivos, tá?

---

\- O processamento (tanto das mensagens nas filas ou dos arquivos) precisa ser idempotentes! Ou seja, se a mesma mensagem ou arquivo for processado duas ou mais vezes, o saldo e os lançamentos precisam permanecer corretos.

---

\- Inicialmente, existe uma restrição de runtime em que a primeira versão da solução precisa ter todos os componentes compartilhando o mesmo processo (API, daemons, consumidores, etc) – exceto o banco.

---

\- 4 meses após o lançamento da primeira versão, os componentes devem ser executados em processos distintos – runtimes dedicados –, inclusive com execuções individuais de CI/CD. E essa mudança de um runtime compartilhado para runtimes dedicados precisa ser a mais rápida possível!

---

\- A solução deve funcionar adequadamente com distribuição de carga entre vários nós/servidores. Ou seja, deve escalar horizontalmente, tratar condições de corrida e possuir o mínimo possível de estado nos nós que não sejam os de banco de dados.

\- Use o banco de dados que quiser.

---

\- Use a lang/stack que quiser.

\- Não negligencie a observabilidade: métricas, logs, e talvez rastreabilidade.

---

\- Lembra dos até 90 dias de lançamentos? Tudo que for anterior a isso, mova do banco onde estão os lançamentos para um armazenamento mais barato. E tudo que for anterior a 3 anos, expurgue – exclua definitivamente.

---

É isso, gente. Eu poderia ficar horas e horas inventando requisitos, mas a thread ficaria enorme. De toda forma, acredito que tenha conseguido inventar um desafio com requisitos realistas pra vc poder estudar/praticar/pensar. E claro!, adicione seus requisitos também, se quiser.

---

Queria agradecer de coração se você leu até aqui e/ou me acompanha dando essa moral, sabe? É por você e pelo compartilhamento de experiências que escrevo esse tipo de conteúdo.  ♥️

Muito obrigado! 🥹






