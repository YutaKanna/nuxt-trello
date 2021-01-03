<template>
  <div id="app">
    <draggable element="ul">
      <li v-for="task in tasks">{{ task }}</li>
    </draggable>
  </div>
</template>

<script>
import draggable from 'vuedraggable';

export default {
  name: 'app',
  components: {
    draggable,
  },
  data() {
    return {
      tasks: [
        'task1',
        'task2',
        'task3',
        'task4',
      ]
    }
  }
}
</script>