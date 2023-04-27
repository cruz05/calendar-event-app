<template>
<h1>Calendar</h1>
<div id="app">
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
