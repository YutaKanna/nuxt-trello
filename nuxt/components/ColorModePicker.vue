<template>
  <div>
    <li
      v-for="color of colors"
      :key="color"
      @click="$colorMode.preference = color"
    >{{color}}</li>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        colors: ['system', 'light', 'dark', 'sepia']
      }
    }
  }
</script>