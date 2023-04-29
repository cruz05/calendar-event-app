<template>
	<div class="rounded-sm px-3 py-1 text-center" :style="getEventBackgroundColor">
		<h2>{{ event.details }}</h2>
		<div>
			<button @click="editEvent(day.id, event.details)">
				<i class="fa fa-edit"></i>
			</button>
			<button @click="deleteEvent(day.id, event.details)">
				<i class="fa fa-trash"></i>
			</button>
		</div>

		<div v-if="event.edit">
			<input type="text" :placeholder="event.details" v-model="newEventDetails" />
			<div class="has-text-centered icons">
				<i
					class="fa fa-check"
					@click="updateEvent(day.id, event.details, newEventDetails)"
				></i>
			</div>
		</div>
	</div>
</template>

<script>
import { store } from "../store";
export default {
	name: "CalendarEvent",
	props: ["event", "day"],
	computed: {
		getEventBackgroundColor() {
			const colors = ["#FF9999", "#85D6FF", "#99FF99"];
			let randomColor = colors[Math.floor(Math.random() * colors.length)];
			return `background-color:${randomColor}`;
		},
	},
	data() {
		return {
			newEventDetails: this.event.details,
		};
	},
	methods: {
		deleteEvent(id, details) {
			store.deleteEvent(id, details);
		},
		editEvent(dayId, details) {
			store.editEvent(dayId, details);
		},
        updateEvent(dayId, details, newEventDetails){
            if(newEventDetails)
                 store.updateEvent(dayId, details, newEventDetails);
            else
                this.event.edit=false;
        }
	},
};
</script>
