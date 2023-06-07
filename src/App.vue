<script>
  import Header from './Components/Header.vue';
  import Tasks from './Components/Tasks.vue';

  export default {
    name: 'App',
    components: {
      Header,
      Tasks,
    },
    methods: {
      toggleComplete(id) {
        this.tasks = this.tasks.map((task) => task.id === id ? { ...task, complete: !task.complete } : task)
      }
    },
    data() {
        return {
            tasks: [],
        }
    },
    created() {
        this.tasks = [
          {
            id: 1,
            text: 'Watch',
            complete: false
          },
          {
            id: 2,
            text: 'Binge',
            complete: true
          },
          {
            id: 3,
            text: 'asdf',
            complete: false
          },
        ]
    }
  }
</script>

<template>
  <Header />
  <Tasks 
    @toggle-complete="toggleComplete"
    :tasks="tasks" />

  <p>{{ this.tasks.length }} item/s left</p>
</template>

<style scoped>
</style>
