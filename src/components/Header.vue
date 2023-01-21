<template>
  <header>
    <h1>{{title}}</h1>
    <Button text="Add task" color="green"/>
    <Button text="Update task" color="blue"/>
    <Button text="Delete task" color="red"/>
  </header>
</template>
<script>
import Button from "@/components/Button.vue";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Header',
  props: {
    title: {
      type: String,
      default: 'Hello World'
    }
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