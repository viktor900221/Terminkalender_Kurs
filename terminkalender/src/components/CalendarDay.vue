<template>
    <div class="card">
              <div class="card-header text-center" role="button">
                <strong>{{day.fullName}}</strong>
              </div>
              <div class="card-body">
                <CalendarEvent v-for="event in day.events" :key="event.title" :event="event"></CalendarEvent>
              </div>
    </div>

    
</template>

<script>
import CalendarEvent from './CalendarEvent.vue';
export default {
name: "CalendarDay",
components: {
    CalendarEvent,
},
//Array-Schreibweise nicht zu empfehlen
/*props:["day"],*/
props: {
    day: {
        type: Object,
        required: true,
        //Bei primitiven Datentypen: default: 100
        //Bei nicht-primitiven Datentypen

        default: function () {
            return {
                id: -1,
                fullName: "Fehlender Wochentag",
                events: [],
            }
        },
        validator: function(value){
            if(Object.keys(value).includes("id")){
                return true;
            }
        },
    }
    
}
}
</script>

<style scoped>

</style>