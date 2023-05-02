<template>
<form @submit.prevent="addEvent" class="mx-auto flex flex-col w-[200px] border border-green-600 p-2">
    <input type="text"  placeholder="New Event" required>
    <p>Day of event: {{ getActiveDayTitle }}</p>
    <input type="submit" class="bg-green-700 hover:cursor-pointer">
</form>
</template>
<script>
import {store} from '../store'

export default{
    name:'CalendarEntry',
    computed:{
        getActiveDayTitle() {
            return store.getActiveDay().fullTitle
        }
    },
    methods:{
        addEvent(e) {
            //e.preventDefault()
            store.submitEvent(e.target[0].value);
            e.target.reset();
        }
    }
}
</script>

