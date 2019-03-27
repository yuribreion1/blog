---
layout: post
title:  começando com vue.js
date:   2019-03-26 23:40:16
description: trabalhando com frameworks client-side
---
### Criação de uma _single page application_ com Vue.js
<br>
- Abrir o _vscode_
- Acessando o terminal a partir da pasta do projeto executar `npm install @vue/cli -g`
- `./node_modules/.bin/vue create meu_site`
- Acessar a sua pasta `cd meu_site`
- Executar usando `npm run serve`

Se der certo você vai receber:

```
  App running at:
  - Local:   http://localhost:8080/
  - Network: http://172.16.58.124:8080/
```

Com o _node js_ podemos injetar arquivos _Javascript_ como o uso do `require`

Outra forma de instalar e inicializar um novo projeto pode ser feito da seguinte forma:

- `vue init webpack-simple <nome>` criando um projeto no molde webpack
- `cd <nome>` para acessar o projeto
- `npm i` para instalar as dependencias
- `npm run dev` sobe um servidor e abre no nosso navegador

- Notamos que foi gerado um arquivo chamado `App.vue` que é renderizado dentro do _main.js_
- Os atributos da tag são as propriedades do componente

### Criamos uma nova propriedade: 

``` html
<template>
    <Mensagem msg="Aqui é a minha propriedade"/>
</template>
<script>
    import Mensagem from './components/Mensagem.vue'

    export default {
  name: 'app',
  components: {
    HelloWorld,
    Mensagem
  }
}
</script>
```

- Dentro do `Mensagem.vue`: 

``` html
<template>
    <div class="bloco">
        {{ msg }}
    </div>
</template>

<script>
export default {
    name: 'Mensagem',
    props: {
        msg: String
    }
}
</script>

<style>
.bloco {
    color: red;
}
</style>

```

**Dentro do arquivo `.vue` a propriedade _scaffold_ já cria a estrutura correta, instalar o [vetur](https://github.com/vuejs/vetur)**

## Outro componente para incorporar um video

- `Youtube.vue`

``` html
<template>
    <iframe :src="url" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
</template>

<script>
export default {
    name: 'Youtube',
    props: {
        url: String
    }
}
</script>

<style>

</style>

```

- `App.vue` 

``` html
<template>
  <div id="app">
    <Youtube url="https://player.vimeo.com/video/322667805"/>
  </div>
</template>

<script>
import Youtube from './components/Youtube.vue'

export default {
  name: 'app',
  components: {
    Youtube
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

```

Outra propriedade além do Props, é a `data` que pode guardar um objeto, que é um estado do seu componente:

``` javascript 
export default {
    data(){
        return {
            nome: "Um nome qualquer",
            idade: 30
        }
    }
}
```

- Além destes, podemos criar métodos(comportamentos) que podem ser usados na nossa pagina são os `methods`:

``` javascript
<script scoped>
export default {
    data(){
        return {
            numero: 0,
            nome: "Yuri Breion"
        }
    }, 
    methods: {
        decrementar() {
            if (this.numero > 0) {
                this.numero = this.numero - 1;
            } else {
                alert("Não é possível decrementar de zero")
            }
        }, 
        incrementar() {
            this.numero = this.numero + 1;
        } 
    }, 
    computed: {
        campo(){
            return this.numero > 0 ? "positivo" : "negativo";
        }
    }
}
</script>
```

No caso aciona foram criados dos métodos, o `incrementar` e o `decrementar` que manipulam o atributo `numero` passado em `data()`

Em nosso template, estamos acionando estes métodos em dois botões, um para adicionar e outro para remover: 

``` javascript
<template class="uk-container">
    <div class="uk-container">
        <!-- Passando um valor direto usando v-model, pega de data -->
        <input type="text" v-model="nome">
        <br>

        <!-- Criando botões que ao clicar chamam o metodo definido no script -->
        <button class="uk-button uk-button-default" v-on:click="decrementar">Decrementar</button>
        <p :class="campo">{{ numero }}</p>
        <button class="uk-button uk-button-default" v-on:click="incrementar">Incrementar</button>
    </div>
</template>
```

O código usado como referência aqui, você acha no [meu git](https://github.com/yuribreion1/vue)