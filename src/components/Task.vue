<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>{{task.text}}
    <i class="fas fa-times"></i>
    </h3>
    <p>{{task.day}}</p>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Task',
  props: {
    task: Object
  }
}
</script>

<style scoped>
.fas {
  color: red;
}
.task{
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder{
  border-left: 5px solid green;
}
.task h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>