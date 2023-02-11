<template>
<div :key="task.id" v-for="task in tasks">
  <Task @delete-task="$emit('delete-task', task.id)" :task="task"/>
</div>
</template>

<script>
import Task from "@/components/Task.vue";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Tasks',
  props: {
    tasks: Array
  },
  components: {
    Task
  },
  emits: ['delete-task']
}
</script>