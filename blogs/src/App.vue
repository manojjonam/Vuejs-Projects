<template>
    <div>
      <router-view></router-view>
    </div>
</template>

<script>
import addBlog from './components/addBlog.vue'
import showBlog from './components/showBlog.vue'
import listBlog from './components/listBlogs.vue'
export default {
    components: {
      'add-Blog':addBlog,
      'show-Blog':showBlog,
      'list-Blog':listBlog
    },
  data () {
    return {

    }
  }
}
</script>

<style >
body{
  margin: 0;
  font-family:'Nunito SemiBold';
}
</style>
