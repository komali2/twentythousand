

<template>
  <div class="hello alert-success">
    Hi
    <button class="btn btn-primary">Test</button>
    <input-with-descriptor v-model="input_1" label="Test descriptor"></input-with-descriptor>
    {{input_1}}
  </div>
</template>

<script>
import InputWithDescriptor from '@/components/InputWithDescriptor.vue'

export default {
  name: 'HelloWorld',
  components: {
    InputWithDescriptor
    },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      input_1: '',
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
