<template>
  <form-helper>
<!--  <h2>hello</h2>
  <p>slllooottt!!!!</P> -->
    <div slot="form-header">
      <h3>this is the title of the form</h3>
      <p>information about the form</p>
    </div>
    <div slot="form-feilds">
      <input type="text" placeholder="name" required/>
      <input type="password" placeholder="password" required/>
    </div>
    <div slot="form-controls">
      <button>submit</button>
    </div>
  </form-helper>
</template>

<script>
import formHelper from './components/formHelper.vue'
export default {
  components:{
    'form-helper': formHelper
  },

  data () {
    return {

      }
   }
 }
</script>
<style scoped>

</style>
