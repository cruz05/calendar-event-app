<template>
<div class="border bg-green-400 rounded-sm px-3 py-1 text-center">
    <h2>{{ event.details }}</h2>
    <i class="fa fa-edit"></i>
    <span><i class="fa fa-trash"></i></span>
</div>
</template>

<script>
export default {
    name:'CalendarEvent',
    props: ['event', 'day']
}
</script>
