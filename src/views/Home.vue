

<template>
  <div class="">
    <div class="row">
      <input-with-descriptor 
        v-model.number="hours_day" 
        label="How many hours a day are you able to practice?" 
        placeholder="Hours/Day" 
        class="col-xs-3 mt-1"
        >
      </input-with-descriptor>
    </div>
    <div class="row">
      <input-with-descriptor 
        v-model.number="days_week" 
        label="How many days a week can you practice? " 
        placeholder="Days/Week"
        class="col-xs-3 mt-1"
        ></input-with-descriptor>
    </div>
    <div class="row">
      <input-with-descriptor 
        v-model.number="hours_goal" 
        label="How many hours are you trying to achieve? (20,000 = 'expert')" 
        placeholder="Desired Hours"
        class="col-xs-3 mt-1"
        ></input-with-descriptor>
    </div>
    <effort-card
      card_title="Effort Needed"
      :hours_goal="hours_goal"
      :hours_week="hours_week"
      :days_in_year="days_in_year"
      :years_until_complete="years_until_complete"
    ></effort-card>

  </div>
  
</template>

<script>
import InputWithDescriptor from '@/components/InputWithDescriptor.vue'
import EffortCard from '@/components/EffortCard.vue'

export default {
  name: 'Home',
  components: {
    InputWithDescriptor,
    EffortCard,
    },
  data () {
    return {
      hours_day: 0,
      days_week: 0,
      hours_goal: 20000
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
      return (Number(this.hours_goal) / this.hours);
    },
    days_until_complete: function(){
      return this.weeks_until_complete * 7;
    },
    weeks_until_complete: function(){
      return this.worked_days_needed / this.days;
    },
    years_until_complete: function(){
      return Number((this.days_until_complete / 365).toPrecision(2));
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
