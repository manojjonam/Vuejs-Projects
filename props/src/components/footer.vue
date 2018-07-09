<template>
<footer>
   <p>{{ copyrights }} {{ title }}</p>
</footer>
</template>

<script>
import  { bus} from '../main';
export default {
       props:{
         title:{
           type:String
         }
       },
  data () {
    return {
        copyrights:'@copyrights 2018'
    }

  },
  created() {
    //do something after creating vue instance
    bus.$on('titleChanged',(data)=>{
      this.title=data;
    })
  }
}
</script>

<style scoped>
footer{
  padding: 10px;
  background: #222;
  }
  p{
    color:lightgreen;
    text-align: center;
  }
</style>
