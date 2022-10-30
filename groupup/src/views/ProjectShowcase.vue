<template>
    <div class="big-wrapper flex-center-column">
        <h2 class="small-title" >{{project.name}}</h2>

        <div class="suggestions" >
            <div class="single-activity-card" v-for="activity in project.activities" >
                {{activity}}
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        data() {
            return {
            project: [],
            }
        },
        methods: {

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
