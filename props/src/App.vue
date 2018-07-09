<template>
  <div>
   <app-header :title="title" v-on:changetitle="updatedtitle($event)"></app-header>
   <app-ninja :ninjas="ninjas" :title="title"></app-ninja>
   <app-footer :title="title"></app-footer>
  </div>
</template>

<script>
import Header from './components/header.vue';
import Footer from './components/footer.vue';
import Ninja from './components/ninjas.vue';
export default {
components:{
 'app-header':Header,
  'app-footer':Footer,
  'app-ninja':Ninja
},
  data () {
    return {
      ninjas:[
        {name:'manoj',speciality:'Vue component',show:false},
        {name:'mario',speciality:'HTML wizard',show:false},
        {name:'ryu',speciality:'click event',show:false},
        {name:'sid',speciality:'condition',show:false},
        {name:'sam',speciality:'Webpack',show:false}
      ],
     title:"vue ninjas"
   }
 },
   methods: {
     updatetitle:function(updatedtitle){
       this.title=updatedtitle;
     }
   }

}
</script>

<style>

</style>
