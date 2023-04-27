<template>
<div id="calendar-day">
    <div>
        <div>{{ day.abbvTitle }}</div>
        <div>{{ day.id }}</div>
        <div>
            <CalendarEvent v-if="day.events.length > 0" v-for="(event, index) in day.events"
            :key="index"
            :event="event"
            :day="day"/>

            <p v-else>No events</p>
        </div>
    </div>
</div>
</template>
<script>
import CalendarEvent from './CalendarEvent.vue';

export default{
    name: "CalendarDay",
    props: ["day"],
    components: { CalendarEvent }
}
</script>