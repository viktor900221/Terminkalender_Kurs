<template>
  <div id="calender-week">
          <div class="card-group">
                 <!-- Anfang: Template für die Calendar-Day-Component -->
            <CalendarDay v-for="day in calendarWeekData" :key="day.id" :day="day"></CalendarDay>
           
            <!-- Ende: Template für die Calendar-Day-Component -->
          </div>
        </div>
</template>

<script>
import CalendarDay from './CalendarDay.vue';
import Store from '../store';

export default {
name: "CalendarWeek",
components:{
    CalendarDay,
}, 
data: function (){
return {
  calendarWeekData: Store.state.calendarWeekData,
}
}
}
</script>

<style scoped>

</style>