<template>
    <div class="big-wrapper flex-center-column">
        <h1 id="main-title" >Login</h1>
        <form action="" class="flex-center-column ">
        <p class="classic-text">Enter your email</p>
        <br>
        <input v-model="name" class="text-input" type="email" >
        <p class="classic-text">Enter your password</p>
        <br>
        <input v-model="password" class="text-input" type="password">
        <br>
        <input class="classic-input" v-on:click="login()" type="button" value="Login">
        <input class="classic-input" type="button" value="Register" v-on:click="register()">
        </form>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        data() {
            return {
            email: '',
            name: '',
            }
        },
        methods: {
            login: function(){
            axios.post('http://127.0.0.1:8000/api/login', {
                email: this.email,
                name: this.name,
            })
            .then(function (response) {
                console.log(response);
            })
            .catch(function (error) {
                console.log(error);
            }); 
            },
            
        },
        methods: {
            register: function(){this.$router.push({ path: '/register', query: {}})}
        }
    }
</script>

<style scoped>
    @import '../assets/main.css';
    
</style>
