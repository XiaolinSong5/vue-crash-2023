<template>
  <header>
    <h1>{{title}}</h1>
  </header>
</template>
<script>

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Header',
  props: ['title']
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