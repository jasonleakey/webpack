{{#pug}}
<template lang="pug">
  #app
    img(src="./assets/logo.png")
    {{#router}}
    router-view
    {{else}}
    HelloWorld
    {{/router}}
</template>
{{else}}
<template>
  <div id="app">
    <img src="./assets/logo.png">
    {{#router}}
    <router-view/>
    {{else}}
    <HelloWorld/>
    {{/router}}
  </div>
</template>
{{/pug}}

<script>
{{#unless router}}
import HelloWorld from './components/HelloWorld'

{{/unless}}
export default {
  name: 'App'{{#router}}{{else}},
  components: {
    HelloWorld
  }{{/router}}
}
</script>

<style lang="scss">
  {{#bootstrap}}
  @import "~bootstrap/scss/bootstrap";
  @import "./assets/custom-bootstrap";
  {{/bootstrap}}

  #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
