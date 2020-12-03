<img src="https://miro.medium.com/max/3840/0*V2joFeJ1WYYRl8tV.png"/>

<h2 align="center">Aprendendo VUE.js</h2>

### Primeiros passos

1. Começamos importando o frame dentro do primeiro script

2. Abrimos uma tag html e declaramos um id que fará a conexão com o Vue

3. Abrimos outro script para iniciar o Vue de fato, nele temos a tag `el` que receberá o id e `data`, onde teremos os nossos dados.

4. Por fim, o que estamos fazendo é renderizando a string contida em message entre as chaves `{{ message }}`

```javascript
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<div id="app">
  <p>{{ message }}</p>
</div>

<script>
  new Vue({
    el: "#app",
    data: {
      message: 'Ola, mundo Vue' + new Date().toLocaleString()
    }
  })
</script>
```

### Usando diretivas

#### Para mostrar uma mensagem em seguida de um hover

```html
...

<div id="app" v-bind:title="message">
  <p>Passe por aqui para ver a mensagem</p>
</div>

<script>
  new Vue({
    el: "#app",
    data: {
      message: "Ola, mundo Vue" + new Date().toLocaleString(),
    },
  });
</script>
```

#### Usando if

```html
...

<div id="app" v-if="see">
  <p>Voce só pode ver isso se 'see' for true</p>
</div>

<script>
  new Vue({
    el: "#app",
    data: {
      see: true,
    },
  });
</script>
```

#### Usando loops

```html
...

<div id="app">
  <ol>
    <li v-for="item in items">{{ item.text }}</li>
  </ol>
</div>

<script>
  var app = new Vue({
    el: "#app",
    data: {
      items: [{ text: "primeiro" }, { text: "segundo" }, { text: "terceiro" }],
    },
  });
</script>
```

### Ouvindo eventos

1. Aqui estamos usando um botão para ouvir o evento `onClick` pelo `v-on:click`.

2. Quando esse evento acontecer, chamamos a função `invert`, pegamos a mensagem com `this.message` e a invertemos.

```html
<div id="app">
  <p>{{ message }}</p>
  <button v-on:click="invert">Inverter string</button>
</div>

<script>
  new Vue({
    el: "#app",
    data: {
      message: "Ola, mundo Vue",
    },
    methods: {
      invert() {
        this.message = this.message.split("").reverse().join("");
      },
    },
  });
</script>
```

### Escutando o valor de um elemento

Com v-model conseguimos escutar o valor de `inputValue` e atualizar o que aparece na tela dentro da tag `p` automaticamente.

```html
...
<div id="app">
  <p>{{ inputValue }}</p>
  <input v-model="inputValue" />
</div>

<script>
  new Vue({
    el: "#app",
    data: {
      inputValue: "valor default",
    },
  });
</script>
```

### Criando e executando a versão CLI do VUE

Instale o VUE na sua máquina de acordo com a [documentação](https://cli.vuejs.org/guide/installation.html)

Depois, crie o projeto com:

```bash
vue create <nome-do-projeto>
```

Em seguida, o VUE vai te perguntar algumas coisas para configurar e instalar as dependencias do projeto. Depois disso, entre na pasta e execute:

```bash
cd <nome-do-projeto> && yarn server
```

### Usando o onChange 

```javascript
<textarea v-model="comment" id="comment"/>
    
watch: {
  // sempre que o comentário mudar, essa função será executada
  comment: function () {
    console.log(this.comment)
  }
},
```
