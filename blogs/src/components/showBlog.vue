<template>
    <div v-theme:column="'wide'" id="show-Blog">
      <h1>All blog Articles</h1>
      <input type="text"  v-model="search" placeholder="search Blog"/>
      <div v-for="blog in filterBlogs" class="single-Blog" v-bind:key="">
        <h2 v-rainbow>{{ blog.title| to-uppercase}}</h2>
        <article>{{ blog.body| snippet }}</article>
      </div>
    </div>
</template>

<script>
import searchMixin from '../mixins/searchMixins';

export default {
    components: {
    
    },
  data () {
    return {
      blogs:[],
      search:''
    }
  },
  methods:{

  },
  created(){
      this.$http.get('https://jsonplaceholder.typicode.com/posts').then(function(data){
          
          this.blogs= data.body.slice(0,10);
      })
  },
  mixins:[searchMixin],
  computed:{
     
  },
}
</script>

<style >
#show-Blog{
    max-width: 800px;
    margin: 0 auto;
}
.single-Blog{
    padding: 20px;
    margin: 20px 0;
    box-sizing: border-box;
    background: #eee;
}
</style>
