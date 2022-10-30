<template>
    <div class="big-wrapper flex-center-column">
        <h1 id="main-title" >Create a new Plan</h1>
        <form action="" class="flex-center-column ">
        <p class="classic-text"> Plan name</p>
        <br>
        <input v-model="name" class="text-input" type="text" >
        <p class="classic-text">Plan start date</p>
        <br>
        <input v-model="start" class="text-input" type="date">
        <br>
        <p class="classic-text">Plan end date</p>
        <br>
        <input v-model="end" class="text-input" type="date">
        <br>
        <input class="classic-input" v-on:click="createProject()" type="button" value="Create">
        </form>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        data() {
            return {
            name: '',
            start: '',
            end: ''
            }
        },
        methods: {
            createProject: function(){
                console.log(this.name, this.start, this.end)
            axios.post('http://127.0.0.1:8000/api/login', {
                end: this.end,
                start: this.start,
                name: this.name,
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
