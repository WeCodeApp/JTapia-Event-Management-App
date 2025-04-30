<template>
  <div class="flex items-center justify-center min-h-screen bg-blue-100">
    <div class="container mt-5">
      <h1 class="mb-4 text-center text-3xl font-bold">Event Management App</h1>

      <AddEvent :events="events" />
      <EventList :events="events" />
    </div>
  </div>
</template>

<script>
import AddEvent from './components/AddEvent.vue'
import EventList from './components/EventList.vue'
import eventsData from './data/events.json'

export default {
  components: {
    AddEvent,
    EventList
  },
  data() {
    return {
      events: eventsData.map(event => ({
        ...event,
        likes: 0
      }))
    }
  }
}
</script>