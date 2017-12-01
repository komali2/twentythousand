

<template>
  <div class="">
    <div class="row">
      <input-with-descriptor 
        v-model="hours_day" 
        label="How many hours a day are you able to practice?" 
        placeholder="Hours/Day" 
        class="col-xs-3"
        >
      </input-with-descriptor>
    </div>
    <div class="row">
      <input-with-descriptor 
        v-model="days_week" 
        label="How many days a week can you practice? " 
        placeholder="Days/Week"
        class="col-xs-3"
        >
      </input-with-descriptor>
    </div>
    Working {{hours_week}} hours a week, or {{hours_day}} hours a day for {{days_in_year}} days of the year, 
    it will take you approximately {{years_until_complete}} years, or {{worked_days_needed}} worked days to achieve 20000 hours. 
    In {{weeks_until_complete}} weeks, you will have achieved your goal. That's {{days_until_complete}} days away.
    <div>
      <ul class="list-group">
        <li class="list-group-item d-flex justify-content-between align-items-center">
          Hours worked per week
          <span class="badge badge-primary badge-pill">{{hours_week}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
          Days worked per year
          <span class="badge badge-primary badge-pill">{{days_in_year}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
          Years Until Complete
          <span class="badge badge-primary badge-pill">{{years_until_complete}}</span>
        </li>
      </ul>
    </div>

  </div>
  
</template>

<script>
import InputWithDescriptor from '@/components/InputWithDescriptor.vue'
const HOURS_CONST = 10000;

export default {
  name: 'HelloWorld',
  components: {
    InputWithDescriptor
    },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      hours_day: 0,
      days_week: 0,
    }
  },
  computed: {
    hours: function(){
      return Number(this.hours_day);
    },
    days: function(){
      return Number(this.days_week);
    },
    hours_week: function(){
      return this.hours * this.days;
    },
    days_in_year: function(){
      // return 365 - ((7 * 52) - (days * 52));
      return this.days * 52;
    },
    hours_worked_per_year: function(){
      return hours_worked = this.hours * this.days_in_year; 
    },
    worked_days_needed: function(){
      return (HOURS_CONST / this.hours);
    },
    days_until_complete: function(){
      return this.weeks_until_complete * 7;
    },
    weeks_until_complete: function(){
      return this.worked_days_needed / this.days;
    },
    years_until_complete: function(){
      return (this.days_until_complete / 365).toPrecision(2);
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
