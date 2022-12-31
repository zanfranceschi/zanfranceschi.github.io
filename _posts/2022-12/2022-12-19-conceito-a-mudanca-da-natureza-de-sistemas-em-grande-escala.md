---
layout: post
title:  "[Conceito] - A Mudança da Natureza de Sistemas em Grande Escala"
date:   2022-12-19
categories: conceitos
tags: conceito
---
> Conteúdo original em [https://twitter.com/zanfranceschi/status/1604825135814279168](https://twitter.com/zanfranceschi/status/1604825135814279168)

---

Ei dev,

Esses dias, nosso amigo @coproduto falou sobre problemas de escalabilidade pra quando as coisas mudam de grandeza. Isso me inspirou a fazer essa thread que é uma introdução básica sobre o tema. Cola aí, que é um assunto legal!

cc @sseraphini

↓

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bpvkqtiikcnzd64zp53z.png)

---

Uma "grandeza superior" ou "grande escala" são termos subjetivos. Então, a gente precisa primeiro entrar num consenso sobre o que é isso.

Pra essa thread, vamos definir grande escala como algo que não cabe dentro dos limites mais comuns.

---

Vou começar com um exemplo bem simplista.

Lembra da época em que os processadores eram de 32 bits e o máximo de memória RAM que a gente conseguia usar eram 4GB? 🥲

4GB é um exemplo de limite.

---

Agora imagina que você desenvolveu uma aplicação que faz algum processamento dentro de um servidor de 32 bits com 4GB de RAM. Essa aplicação usa no máximo uns 2 dos 4GB disponíveis de RAM. Mas aí, vem um requisito novo que vai exigir uns 20GB de RAM pro processamento. E agora?

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/4pxyj7l1jpxck1h6rryw.png)

---

Como você atingiu um limite, você precisará fazer alguma coisa diferente – ou seja, mudar a natureza da solução do seu problema. Usar um servidor de 64 bits, computação distribuída, processar partes menores por vez, ou outra abordagem.

---

Outro exemplo talvez um pouco mais próximo do nosso dia a dia. Você tem um número de clientes e demanda computacional em que um banco de dados relacional atende adequadamente às requisições de escrita ao passo das requisições HTTP.

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hpj0xg51uugdph2q6n70.png)

---

Agora, vamos supor que a demanda aumente ao ponto de ultrapassar a capacidade de escritas síncronas necessárias no banco de dados. A natureza da solução precisa mudar, pois ultrapassamos um limite. Talvez alguma coisa como o exemplo do fluxo seguinte seja necessária.

![Image](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/dekws3ogq3iji7kyoqs2.png)

---

É um desafio muito interessante trabalhar num projeto/produto que muda de escala. Geralmente, a mudança é gradual e a gente vai mudando aos poucos a natureza da solução.

Mudanças bruscas de escala são mais raras, mas podem acontecer.

---

Existem escalas e escalas, né? Os dois exemplos que dei não testam limites, por exemplos, de infraestrutura básica como redes, armazenamentos, eletricidade, temperatura, etc.

O que provedores cloud hoje em dia nos oferecem, geralmente é mais do que suficiente pra casos comuns.

---

Agora tenta imaginar a busca do Google. São bilhões de buscas por dia no mundo todo! Não me surpreenderia se me dissessem que têm requisitos especiais de resfriamento, eletricidade, etc. Deve ser um negócio de outra grandeza que a maioria de nós nem imagina.

---

Quando o nosso Polvo Sensato 🐙♥️ diz que a natureza das coisas muda em grande escala, é sobre as mudanças necessárias pra superar esses limites que estamos falando.

---

Bom, é isso o que tinha pra falar sobre grandeza de problemas, escalas, etc. Obrigado demais se você leu até aqui!

Um beijo pra quem é de beijo, um abraço pra quem é de abraço. 💕

---

Ah, e tá aqui o post do @coproduto que me inspirou a fazer essa thread👇

https://twitter.com/coproduto/status/1601968298903552001

Brigado, Polvo.