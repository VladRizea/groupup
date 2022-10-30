<template>
    <div class="big-wrapper flex-center-column">
        <h2 class="small-title" >My plans</h2>

        <div class="suggestions" >
            <input class="classic-input" type="button" value="Create Plan" v-on:click="createProject()">
            <div class="single-activity-card" v-for="project in projects" >
                <input class="classic-input" v-on:click="debateProject(project)" type="button" value="Debate">
                {{project.name}}
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        data() {
            return {
            projects: [{name:'fasdf', id:'12345'}, {name:'fasdfasdf', id:'12345'}],
            }
        },
        methods: {
            createProject: function(){
                this.$router.push({ path: '/createproject', query: {}})
            },
            debateProject: function(project){
                this.$router.push({ path: '/debate', query: { id: project.id }})
                console.log(this.$route.query.id) // outputs 'yay'
            }
        }
    }
</script>

<style scoped>
    @import '../assets/main.css';
    .single-activity-card{
        font-size: 30px;
    }
    .icon-x{
        padding: 5px;
        background-color: #EF476F;
        height: 40px;
        width: 40px;
        border-radius: 1000px;
        color: white;
        text-align: center;
    }
    .icon-plus{
        padding: 5px;
        background-color: #118AB2;
        height: 40px;
        width: 40px;
        border-radius: 1000px;
        color: white;
        text-align: center;
    }
    .icon:hover{
        cursor: pointer;
    }
    .top{
        top: 100px;
    }
    .suggestions{
        width: 50vw;
    }
</style>
