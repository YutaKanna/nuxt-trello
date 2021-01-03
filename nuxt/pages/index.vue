<template>
  <div id="app">
    <div id="box1" class="box">
      <draggable tag="ul" :options="{group:'ITEMS'}">
        <li v-for="item, index in items" :key="item.no">{{item.name}}-(No.{{item.no}})</li>
      </draggable>
    </div>
    <div id="box2" class="box">
      <draggable tag="ul" :options="{group:'ITEMS'}">
        <li v-for="item, index in items2" :key="item.no">{{item.name}}-(No.{{item.no}})</li>
      </draggable>
    </div>
  </div>
</template>

<script>
import draggable from 'vuedraggable';

export default {
  name: 'app',
  components: {
    draggable
  },
  data: function () {
    return {
      items:[
        {no:1, name:'キャベツ', categoryNo:'1'},
        {no:2, name:'ステーキ', categoryNo:'2'}
      ],
      items2:[
        {no:5, name:'きゅうり', categoryNo:'1'},
        {no:6, name:'ハンバーグ', categoryNo:'2'}
      ]
    }
  }
}
</script>

<style>
#app {
  padding : 15px;
}

.box {
  width: 50%;
  float: left;
  padding: 20px 0;
}
#box1 {
  background-color: #fdd;
}
#box2 {
  background-color: #ddf;
}

li {
  cursor:pointer;
  padding: 10px;
  border: solid #ddd 1px;
  background-color: #fff;
}
</style>