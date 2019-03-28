---
layout: post
title:  Gerenciamento de dependencias
date:   2019-03-27 21:40:16
description: Mais sobre devOps
---

Uma boa referencia para este assunto encontramos no [_twelve factory_](https://12factor.net/pt_br/).
Quando falamos de dependencias de uma aplicação, temos que separá-las em:
    -   **Internas** 
        -   Bibliotecas/modulos
        -   Configurações
    -   **Externas**
        -   Scripts de configuração para deploy
        -   Banco de dados
        -   Carga de dados(_import_)

Considera-se ideal **isolar** cada dependencia da aplicação, um exemplo para isto é o carregamento de uma biblioteca como [_Bootstrap_](https://getbootstrap.com).
Também é considerado ideal que tudo seja mais especificado possível, seja versão da dependencia, e disponibilidade dela.
Algumas empresas por exemplo, pedem que use bibliotecas externas(_cdn_) para que não tenham dependencias locais, de arquivos carregados na maquina do desenvolvedor. 

Exemplo de CDN do CSS Bootstrap: 
``` html 
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
```

Existem grandes e conhecidos gerenciadores de dependencias, no caso do PHP por exemplo, o [_Composer_](https://getcomposer.org/):

![composer](http://cdn.desenvolvimentoparaweb.com/app/uploads/2012/12/composer-logo.png)

No caso de linguagens mais novas como `Javascript` temos o `node.js` que foi montado já pensado em gerenciamento de dependencias usando o [`Node Package Manager`](https://www.npmjs.com/)

![npm](data:image/jpeg;base64,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)

Podemos pegar uma aplicação e a partir do ponto onde ela for executada, instalar todas as dependencias necessárias, segue exemplo no _node_:

``` javascript
npm i
```

Também há no _Python_ o [_pip_](https://pypi.org/) com a mesma proposta:

![pip](https://pypi.org/static/images/logo-small.6eef541e.svg)

No caso do _Java_ também existem gerenciadores de dependencia como:

-   [_Maven_](https://maven.apache.org/)
-   [_Grandle_](https://gradle.org/)