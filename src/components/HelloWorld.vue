

<template>
  <div class="">
    <div class="row">
      <input-with-descriptor 
        v-model="hours_day" 
        label="How many hours a day are you able to practice?" 
        placeholder="Hours/Day" 
        class="col"
        >
      </input-with-descriptor>
    </div>
    <div class="row">
      <input-with-descriptor 
        v-model="days_week" 
        label="How many days a week can you practice? " 
        placeholder="Days/Week"
        class="col"
        >
      </input-with-descriptor>
    </div>
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
      hours_day: '',
      days_week: '',
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
