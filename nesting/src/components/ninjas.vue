<template>
  <div id="ninjas">
    <ul>
      <li v-for="ninja in ninjas" v-on:click="ninja.show=!ninja.show">
       <h3>{{ ninja.name }}</h3>
       <h2 v-show="ninja.show">{{ ninja.speciality }}</h2>
      </li>
    </ul>

  </div>
</template>

<script>

export default {

  data () {
    return {
      ninjas:[
        {name:'manoj',speciality:'Vue component',show:false},
        {name:'mario',speciality:'HTML wizard',show:false},
        {name:'ryu',speciality:'click event',show:false},
        {name:'sid',speciality:'condition',show:false},
        {name:'sam',speciality:'Webpack',show:false}
      ]

    }
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
