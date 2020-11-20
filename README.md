## Aprendendo VUE.js

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
