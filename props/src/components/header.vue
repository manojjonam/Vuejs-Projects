<template>
 <header>
    <h1 v-on:click="changetitle">{{ title }}</h1>
 </header>
</template>

<script>
import {bus} from'../main'
export default {
  props:{
    title:{
      type:String
    }

  },
  methods:{
    changetitle:function() {
        this.title='vue wizard';
      //this.$emit('titleChanged','vue wizard');
      bus.$emit('titleChanged','vue wizard');
    }
  }

}
</script>

<style scoped>
 header {
   padding: 6px;
   background: lightgreen;
 }
h1{
  color:#222;
  text-align: center;
}
</style>
