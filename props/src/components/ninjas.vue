<template>
  <div id="ninjas">
    <ul>
      <li v-for="ninja in ninjas" v-on:click="ninja.show=!ninja.show">
       <h3>{{ ninja.name }}</h3>
       <h2 v-show="ninja.show">{{ ninja.speciality }}</h2>
      </li>
    </ul>
   <button v-on:click="deleteninja">delete ninja</button>
   <p> {{ title }} </p>
  </div>
</template>

<script>
import {bus} from'../main'

export default {
  props: {
    ninjas:{
      type:Array,
      required:true
    },
    title:{
      type: String
    }
  },
   data() {
    return {

    }

  },
  created() {
    //do something after creating vue instance
    bus.$on('titleChanged',(data)=>{
      this.title=data;
    })
  },
  methods: {
    deleteninja:function(){
      this.ninjas.pop();
    }
  },
  //life cycle hooks
  beforeCreate() {
    //do something before creating vue instance
  alert('beforeCreate');
    },
    created() {
      //do something after creating vue instance
      alert('create');
    },
    beforeMount() {
      //do something before mounting vue instance
      alert('beforeMount');
    },
    mounted() {
      //do something after mounting vue instance
      alert('mounted');
    },
    beforeUpdate() {
      //do something before updating vue instance
      alert('beforeUpaded');
    },
    updated() {
      //do something after updating vue instance
      alert('updated');
    }
  }
</script>

<style>
#ninjas{
  width: 100%;
  max-width: 1200px;
  margin:40px auto;
  padding: 0 20px;
  box-sizing: border-border-box;
}
ul{
  display: flex;
  flex-wrap: wrap;
  list-style-type: none;
  padding: 0;

}
li{
  flex-grow: 1;
  flex-basis: 300px;
  text-align:center;
  padding: 30px;
  border:1px solid #222;
  margin: 10px;
}

</style>
