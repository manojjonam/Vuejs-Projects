<template>
<footer>
   <p>{{ copyrights }}</p>
</footer>
</template>

<script>

export default {

  data () {
    return {
        copyrights:'@copyrights 2018'
    }
  }
}
</script>

<style scoped>
footer{
  padding: 10px;
  background: #222;
  }
  p{
    color:lightgreens;
    text-align: center;
  }
</style>
