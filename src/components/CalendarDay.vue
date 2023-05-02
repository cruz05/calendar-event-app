<template>
<div @click="setActive(day.id)" id="calendar-day" class="border border-gray-400">
    <div class="bg-gray-800 text-white">{{ day.abbvTitle }}</div>
    <div class="p-2 pt-1">
        <p class="text-white text-left">{{ day.id }}</p>
        <div class="flex flex-col gap-2">
            <CalendarEvent v-if="day.events.length > 0" v-for="(event, index) in day.events"
                :key="index"
                :event="event"
                :day="day"/>
                
            <p v-else class="text-white">No events</p>
        </div>
    </div>
</div>
</template>
<script>
import { store } from '../store.js'
import CalendarEvent from './CalendarEvent.vue';

export default{
    name: "CalendarDay",
    props: ["day"],
    components: { CalendarEvent },
    methods: {
        setActive(id) {store.setActiveDay(id)}
    },
}
</script>