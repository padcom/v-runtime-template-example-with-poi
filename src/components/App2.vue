<template>
  <div>
    <textarea v-model="src" style="width: 400px;height: 100px;" />
    <br/>
    <button @click="code = src">Run me</button>
    <hr/>
    <v-runtime-template :template="code"/>
  </div>
</template>

<script>
import Vue from 'vue'
import Component from 'vue-class-component'
import VRuntimeTemplate from 'v-runtime-template'

@Component({
  components: {
    VRuntimeTemplate
  },
})
export default class App extends Vue {
  src = `<div>
  Message: <input type="text" v-model="message"/>
  <h1>{{ message }}/{{ message }} :)</h1>
</div>`
  code = ''

  message = 'Hello, world!'
}
</script>
