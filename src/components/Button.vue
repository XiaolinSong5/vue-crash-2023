<template>
  <button @click="onClick()" :style="{background:color}" class="btn">
    {{ text }}
  </button>
</template>
<script>

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Button',
  props: {
    text: String,
    color: String
  },
  methods: {
    onClick()
    {
      console.log('click');
    }
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
      }
    ];
  }
}
</script>