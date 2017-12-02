<template>
<div class="card mt-3">
    <div class="card-body">
        <h4 class="card-title">{{card_title}}</h4>
    </div>
    <ul class="list-group list-group-flush">
        <li class="list-group-item d-flex justify-content-between align-items-center ">
            Goal Hours
            <span class="badge badge-primary badge-pill">{{hours_goal}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center ">
            Hours worked per week
            <span class="badge badge-primary badge-pill">{{hours_week}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center ">
            Days worked per year
            <span class="badge badge-primary badge-pill">{{days_in_year}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center ">
            Years Until Complete
            <span class="badge badge-primary badge-pill">{{years_until_complete}}</span>
        </li>
    </ul>
</div>
</template>

<!--
    https://vuejs.org/v2/guide/components.html#Dynamic-Props
    When passing in props to this bad boy, do:
        :hours_week"something" :days_in_year="something"
-->

<script>
export default {
    name: 'effort-card',
    //https://vuejs.org/v2/guide/components.html#Prop-Validation
    props: {
        card_title: String,
        hours_week: Number,
        days_in_year: Number,
        years_until_complete: Number,
        hours_goal: {
            type: Number,
            default: 20000,
        },
    },
    data: function(){
        return {

        }
    }
}
</script>