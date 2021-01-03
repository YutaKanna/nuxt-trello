<template>
  <div id="app">
    <draggable tag="ul">
        <li v-for="item, index in items" :key="item.no">{{item.name}}-(No.{{item.no}})</li>
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
        items:[
          {no:1, name:'キャベツ', categoryNo:'1'},
          {no:2, name:'ステーキ', categoryNo:'2'},
          {no:3, name:'リンゴ', categoryNo:'3'}
        ]
    }
  }
}
</script>

<style>
ul {
  list-style-type: none;
}
li {
  cursor: pointer;
  padding: 10px;
  border: solid #ddd 1px;
}
</style>