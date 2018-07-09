<template>
  <div>
    <ul>
      <li v-for="ninja in ninjas">{{ ninja }}</li>
    </ul>
    <h1>{{ name }}</h1>
  </div>
</template>

<script>
export default {
  data () {
    return {
      name: 'manoj',
      ninjas:['yoshi','mario','ryu']
    }
  }
}
</script>

<style scoped >
h1{
  color: green;
}
</style>
