<template>
    <input :placeholder="label" v-model="user_input"></input>
</template>

<script>
export default {
  name: 'input-with-descriptor',
  props: ['label'],
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
