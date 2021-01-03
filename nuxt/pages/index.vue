<template>
  <div id="app">
    <ul id="app">
      <button v-on:click="doAdd">追加</button>
      <draggable>
        <li v-for="item, index in myList" :key="item.no">{{item.name}}-(No.{{item.no}})
          <span class="del" v-on:click="doDelete(index)">[削除]</span>
        </li>
      </draggable>
    </ul>
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
          {no:2, name:'ステーキ', categoryNo:'2'},
          {no:3, name:'リンゴ', categoryNo:'3'}
        ],
        newNo: 4
    }
  },
  computed: {
    myList: function(){
      return this.items;
    }
  },
  methods: {
    doAdd:function(){
      var self = this;
      var no = 0;
          　
      if(self.items.concat().length > 0){
        no =  Math.max.apply(null,self.items.concat().map(function(item){return item.no;})) +1;
        self.newNo = self.newNo < no ? no:self.newNo;
      }

      this.items.push(
        {
          no:　this.newNo,
          name:'追加リスト'+ this.newNo,
          categoryNo:'5'
        }
      );
    },
    doDelete: function(index){
      this.items.splice(index, 1);
    },
  }
}
</script>

<style>
#app {
  padding : 15px;
}

li {
  cursor:pointer;
  padding: 10px;
  border: solid #ddd 1px;
}

.del {
  color: #f00;
}
</style>