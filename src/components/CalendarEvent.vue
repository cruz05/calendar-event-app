<template>
<div class="rounded-sm px-3 py-1 text-center" :style="getEventBackgroundColor">
    <h2>{{ event.details }}</h2>
    <i class="fa fa-edit"></i>
    <span><i class="fa fa-trash"></i></span>
</div>
</template>

<script>
export default {
    name:'CalendarEvent',
    props: ['event', 'day'],
    computed:{
        getEventBackgroundColor() {
            const colors=['#FF9999','#85D6FF','#99FF99']
            let randomColor=colors[Math.floor(Math.random()*colors.length)]
            return `background-color:${randomColor}`
        }
    }
}
</script>
