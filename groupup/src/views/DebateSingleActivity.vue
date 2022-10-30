<template>
    <div class="big-wrapper flex-center-column-top">
        <h2 class="small-title" >Debate</h2>
        <h2 class="small-title" >{{activities[index]}}</h2>

        

    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        data() {
            return {
            activities: ['one', 'two'],
            index: 0
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
            },
            addActivity: function(){
                if(this.name){
                    console.log(this.name)
                    this.activities.push(this.name)
                }
                this.name="";
            },
            removeAcivity: function(activity){
                this.activities.pop(activity);
            },
            addSuggestion: function(activity){
                this.activities.push(activity);
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
