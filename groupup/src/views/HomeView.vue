<template>
  <div class="big-wrapper flex-center-column">
    <h1 id="main-title" >GroupUP</h1>
    <p class="classic-text">Enter a group code:</p>
    <br>
    <form action="" class="flex-center-column ">
      <input  v-model="code" class="text-input" type="text">
      <br>
      <input class="classic-input" type="button" value="Enter!" v-on:click="debate()">
      <input class="classic-input" type="button" value="Login" v-on:click="login()">
    </form>
  </div>

</template>

<script>

export default{
  data() {
    return {
    code: '',
    }
  },
  methods: {
    login: function(){this.$router.push({ path: '/login', query: {}})},
    debate: function(){this.$router.push({ path: '/login', query: {id:this.code}})}
  }
}

</script>

<style>
@import '../assets/main.css';
</style>