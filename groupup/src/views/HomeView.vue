<template>
  <div class="big-wrapper flex-center-column">
    <h1 id="main-title" >GroupUP</h1>
    <p class="classic-text">Enter a group code:</p>
    <br>
    <form action="" class="flex-center-column ">
      <input class="text-input" type="text">
      <br>
      <input class="classic-input" type="button" value="Enter!">
      <input class="classic-input" type="button" value="Login" v-on:click="login()">
    </form>
  </div>

</template>

<script>

export default{
  methods: {
   login: function(){this.$router.push({ path: '/login', query: {}})}
  }
}

</script>

<style>
@import '../assets/main.css';
</style>