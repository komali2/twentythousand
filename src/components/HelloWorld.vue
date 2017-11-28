

<template>
  <div class="hello alert-success">
    Hi
    <button class="btn btn-primary">Test</button>
    <input-with-descriptor label="Test descriptor"></input-with-descriptor>
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
      msg: 'Welcome to Your Vue.js App'
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
