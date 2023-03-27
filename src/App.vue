<template>
  <div class="container">
    <Header @toggle-add-task="toggleAddTask"
            title="Task Tracker" :showAddTask="showAddTask"/>
    <div v-if="showAddTask">
      <AddTask @add-task="addTask"/>
    </div>
    <Tasks @toggle-reminder="toggleReminder"
           @delete-task="deleteTask"
           :tasks="tasks"/>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Tasks from "@/components/Tasks.vue";
import AddTask from "@/components/AddTask.vue";
export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask
  },
  data() {
    return {
      tasks: [],
      showAddTask: true
    }
  },
  methods: {
    addTask(task) {
      this.tasks = [...this.tasks, task];
    },
    deleteTask(id) {
      console.log('task', id);
      if (confirm('Are you sure?')) {
        this.tasks = this.tasks.filter((task) =>
            task.id !== id);
      }
    },
    toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    },
    toggleReminder(id) {
      console.log('toggleReminder', id);
      this.tasks = this.tasks.map((task) => task.id === id ?
          {
            ...task, reminder: !task.reminder
          } : task
      )
    },
    async fetchTasks() {
      const res = await fetch('http://localhost:3000/tasks');
      const data = await  res.json();
      return data;
    }
  },
  async created() {
    this.tasks = await this.fetchTasks();
    // this.tasks = [
    //   {id: 1,
    //     text: 'Doctors appointment',
    //     day: '01-02 14:00',
    //     reminder: true
    //   },
    //   {id: 2,
    //     text: 'Meeting at school',
    //     day: '01-03 14:00',
    //     reminder: true
    //   },
    //   {id: 3,
    //     text: 'Food Shopping',
    //     day: '03-03 11:00',
    //     reminder: false
    //   }
    // ];
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


