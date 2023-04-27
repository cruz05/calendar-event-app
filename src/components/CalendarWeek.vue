<template>
    <div id="calendar-week" class="flex p-2 bg-slate-500">
        <CalendarDay v-for="day in sharedState.seedData" :key="day.id" :day="day"/>
    </div>
</template>
<script>
import {store} from '../store.js'
import CalendarDay from './CalendarDay.vue';

export default{
    name: "CalendarWeek",
    data() {
        return {
            sharedState: store.state
        };
    },
    components: { CalendarDay }
}
</script>