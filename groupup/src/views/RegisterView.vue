<template>
    <div class="big-wrapper flex-center-column">
        <h1 id="main-title" >Register</h1>
        <form action=""  class="flex-center-column ">
        <p class="classic-text">Enter your name</p>
        <br>
        <input v-model="name"  class="text-input" type="text" >
        <p class="classic-text">Enter your email</p>
        <br>
        <input v-model="email"  class="text-input" type="email" >
        <p class="classic-text">Enter your password</p>
        <br>
        <input v-model="password" class="text-input" type="password">
        <p class="classic-text">Enter your password again</p>
        <br>
        <input v-model="passwordsecond" class="text-input" type="password">
        <br>
        <input class="classic-input" v-on:click="click()" type="button" value="Register">
        </form>
    </div>
  </template>
  
  <script>
  import axios from 'a'
    export default {
        data() {
            return {
            email: '',
            name: '',
            password: '',
            passwordsecond: ''
            }
        },
        methods: {
            click: function(){
            axios.post('http://127.0.0.1:8000/api/login', {
                email: this.email,
                name: this.name,
                password: this.password,
                passwordsecond: this.passwordsecond
            })
            .then(function (response) {
                console.log(response);
            })
            .catch(function (error) {
                console.log(error);
            }); 
            }

        }
    }


  </script>

  <style scoped>
    @import '../assets/main.css';
  </style>
  