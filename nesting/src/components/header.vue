<template>
 <header>
    <h1>{{ title }}</h1>
 </header>
</template>

<script>
export default {
  data () {
    return {
      title:'Vue ninja'

    }
  }
}
</script>

<style scoped>
 header {
   padding: 6px;
   background: lightgreen;
 }
h1{
  color:#222;
  text-align: center;
}
</style>
