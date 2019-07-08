<template>
  <div id="app">
    <p>当前最热门的五大网游</p>
    <p>
      <span v-for="(item,index) in list" :key="index" :class="cur==index?'active':''" @click="change(index)">{{item}}</span>
    </p>
    <swiper :cur="cur" :change="change"/>
  </div>
</template> 

<script>

import Swiper from "./components/swiper";

export default {
  name: 'App',
  data(){
    return {
      list:["英雄联盟","贪玩蓝月","守望先锋","穿越火线","绝地求生"],
       cur:0
    }
  },
  components: {
   Swiper
  },
  methods:{
    change(cur){
      this.cur = cur
    }
  }
}
</script>

<style lang="scss">
*{
  padding: 0;
  margin: 0;
  list-style: none;
  box-sizing: border-box;
}
p{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
span{
  &.active{
    color:red;
  }
}
</style>
