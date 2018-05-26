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
import VRuntimeTemplate from 'v-runtime-template'

export default {
  components: {
    VRuntimeTemplate,
  },
  data() {
    return {
      src: `<div>
  Message: <input type="text" v-model="message"/>
  <h1>{{ message }}/{{ message }} :)</h1>
</div>`,
      code: '',
      message: 'Hello, world!',
    }
  }
}
</script>
