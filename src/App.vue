<template>
<div id="app" class="text-center">
    <h1 class="text-2xl font-semibold">Calendar</h1>
    <CalendarWeek/>
    <CalendarEntry/>
</div>
</template>

<script>
import CalendarEntry from './components/CalendarEntry.vue';
import CalendarWeek from './components/CalendarWeek.vue';

export default {
    name: "App",
    components: { CalendarEntry, CalendarWeek }
}
</script>
