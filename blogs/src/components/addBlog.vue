<template>
    <div id="add-Blog">
      <h2>add a new Blog post</h2>
      <form v-if="!submitted">
        <label>Blog Title:</label>
          <input type="text" v-model.lazy="blog.title" required>
        <label>Blog Content:</label>
           <textarea v-model.lazy="blog.Content"></textarea>
         <div id="checkboxes">
            <label>Ninjas</label>
              <input type="checkbox" value="ninjas" v-model="blog.categories"/>
            <label>wizards</label>
              <input type="checkbox" value="wizards" v-model="blog.categories"/>
            <label>mario</label>
              <input type="checkbox" value="mario" v-model="blog.categories"/>
            <label>cheese</label>
              <input type="checkbox" value="spike" v-model="blog.categories"/>
        </div>
        <label>Author</label>
        <select v-model="blog.author">
          <option v-for="author in authors" :key="author"> {{ author }} </option>
        </select>
        <button v-on:click.prevent="post">Add blog</button>
      </form>
      <div v-if="submitted">
      <h3>thanks for adding</h3>
      
      </div>
      <div id="preview">
        <h3>Previe Blog</h3>
        <p>Blog Title:{{ blog.title }}</p>
        <p>Blog Content:{{ blog.Content }}</p>
        <p> blog categories: </p>
        <ul>
          <li v-for="category in blog.categories" :key="category" > {{ category }} </li>
        </ul>
        <p>Author:{{ blog.author }}</p>
      </div>
    </div>
</template>

<script>
export default {

  data () {
    return {
      blog:{
       title:"",
       Content:'',
       categories:[],
       author:""
     },
     authors:["ninja","the angular","jack"],
     submitted:false,
   }
 },
 methods:{
   post:function(){
     this.$http.post('https://jsonplaceholder.typicode.com/posts',{
       title:this.blog.title,
       body:this.blog.Content,
       userid:1
     }).then(function(data){
       console.log(data);
       this.submitted=true;
     });
   }
 }
}
</script>

<style >
#add-Blog *{
  box-sizing: border-box;
}
#add-Blog{
  margin: 20px auto;
  max-width: 500px;
}
label{
  display: block;
  margin: 20px 0 10px;
}
input[type="text"], textarea{
  display: block;
  width: 100%;
  padding: 8px;
}
#preview{
  padding: 10px 20px;
  border: 1px dotted #ccc;
  margin:30px 0;
}
h3{
  margin-top: 10PX;
}
#checkboxes{
  display: inline-block;
  margin-right: 10px;
}
#checkboxes label{
  display: inline-block;
}

</style>
