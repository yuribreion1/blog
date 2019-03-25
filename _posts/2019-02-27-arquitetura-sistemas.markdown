---
layout: post
title:  sistemas monoliticos vs. micro servicos
date: 2019-02-27 21:01:00
description: detalhes importantes e suas diferenças
---

#### Boas práticas de desenvolvimento
<br> 

-   **Agilidade** : Uso de multiplas camadas e plataformas mais granulares a fim de separar camadas como lógica de regras de negócio e interface de usuário ou mesmo funcionalidades dentro de uma interface.
-   **Mobilidade** : Aplicações capazes de serem implementadas em mais de um tipo de plataforma, prontas para o uso de _Cloud Computing_. 
-   **Funcionalidade** : Soluções baseadas em mobile ou interfaces web, que possam ser simplesmente acessadas a partir de um navegador web

#### Sistemas monolíticos
<br>
-   Um sistema composto por diversos modulos e que todos eles estão dentro de um único pacote, vários recursos juntos
    -   Exemplo: Sistema que processa _billing_, _notification_, _case management_. 

As novas empresas cada vez mais tem trabalhado em criar aplicações cada vez mais granularizadas, isso se aplica muito a aplicações _Cloud Native_ usando _Micro servicos_, onde temos várias aplicações onde cada uma tem a sua responsábilidade bem definida.

**Arquitetura monolítica vs. Micro servicos**

<img style="-webkit-user-select: none;cursor: zoom-out;" src="https://cdn-images-1.medium.com/max/2000/1*xu1Ge_Cew0DHdSU6ETcpLQ.png" width="800" height="480">

**Vantagens e desvantagens no uso de micro serviços**

+ Fácil implementação
+ Em  geral é uma solução totalmente _cloud native_

- Muito granular
- Teste de integração se torna muito complexo
- Aumento na curva de aprendizagem 
