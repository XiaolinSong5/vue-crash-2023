<template>
  <header>
    <h1>{{title}}</h1>
    <!-- <Button @toggle-add-task="$emit('toggle-add-task')"-->
    <Button @btn-click="$emit('toggle-add-task')"
            :text="showAddTask ? 'Close' : 'Add Task'"
            :color="showAddTask ? 'red' : 'green'"/>
  </header>
</template>
<script>
import Button from "@/components/Button.vue";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Header',
  props: {
    title: {
      type: String
    },
    showAddTask: Boolean
  },
  components: {
    Button
  }
}
</script>
<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>