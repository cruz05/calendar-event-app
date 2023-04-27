<template>
    <div id="calendar-week" class="mx-auto w-fit flex p-2 bg-gray-600">
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