<template>
  <div class="container">
  <h1>Task Tracker</h1>
    <Header/>
    <Tasks :tasks="tasks"/>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Tasks from "@/components/Tasks.vue";
export default {
  name: 'App',
  components: {
    Header,
    Tasks
  },
  data() {
    return {
      tasks: []
    }
  },
  created() {
    this.tasks = [
      {id: 1,
        text: 'Doctors appointment',
        day: '01-02 14:00',
        reminder: true
      },
      {id: 2,
        text: 'Meeting at school',
        day: '01-03 14:00',
        reminder: true
      },
      {id: 3,
        text: 'Food Shopping',
        day: '03-03 11:00',
        reminder: false
      }
    ];
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>


