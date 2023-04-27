<template>
<form class="mx-auto flex flex-col w-[200px] border border-green-600 p-2">
    <input type="text" placeholder="New Event" required>
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
            console.log(store.getActiveDay().fullTitle)
            return store.getActiveDay().fullTitle
        }
    }
}
</script>

