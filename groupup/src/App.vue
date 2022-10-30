<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>

  <div class="big-wrapper flex-center-column">
    <form action="" class="flex-center-column ">
      <input class="text-input" type="text">
      <br>
      <input class="classic-input" type="submit" value="Enter!">
    </form>
  </div>

</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');

*{
  font-family: 'Poppins', sans-serif;
}
.big-wrapper{
  height: 100vh;
  width: 100vw;

}
.flex-center-column{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.classic-input{
  font-size: 30px;
  padding: 0 20px;
  background-color: #36CA00;
  border-radius: 2000px;
  border: none;
  margin: 30px;
}

.classic-input:hover{
  opacity: 0.6;
  cursor: pointer;
}

.text-input{
  font-size: 34px;
}

</style>
