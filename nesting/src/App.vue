<template>
  <div>
     <app-header></app-header>
     <app-ninja></app-ninja>
     <app-footer></app-footer>
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

    }
  }
}
</script>

<style>

</style>
