---
layout: post
title: Internacionalização
description: Diferentes idiomas para o seu aplicativo
date: 2019-06-07 16:34:00
---

É muito comum acessar aplicativos ou sites que de acordo com o país sejam traduzidos automaticamente, é neste momento que se aplica o conceito de **internacionalização**.

Quando convertemos textos para variáveis, elas ficam guardadas dentro do arquivo **`strings.xml`** na pasta `values`:

![ywRU4.png](https://a.imge.to/2019/06/08/ywRU4.png)

Segue um exemplo do arquivo:

``` xml
<resources>
    <string name="app_name">Internacionalizacao</string>
</resources>
```

Considerando que a idioma principal esta em Português, vamos criar um novo arquivo apontando para a pasta values e o código do idioma, segue exemplo para o Inglês:  `**values-en**`:

![ywrXA.png](https://a.imge.to/2019/06/08/ywrXA.png)

![ywDGU.png](https://a.imge.to/2019/06/08/ywDGU.png)

Agora no arquivo **strings.xml** do idioma que criamos podemos atribuir um valor traduzido.

Uma vez que temos mapeado todos os textos do aplicativo convertidos a variável dentro do arquivo **strings.xml**, podemos traduzi-los da mesma forma.
