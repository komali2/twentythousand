<template>
  <div>
    <label >{{label}}</label>
    <input 
      :placeholder="placeholder" 
      v-model="user_input" 
      class="form-control"
      type="number"></input>
  </div>
</template>

<script>
export default {
  name: 'input-with-descriptor',
  props: ['label', 'placeholder', 'classes'],
  data: function(){
    return {
      user_input: '',
    }
  },
  watch: {
    'user_input': function(){
      this.$emit('input', this.user_input);
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
