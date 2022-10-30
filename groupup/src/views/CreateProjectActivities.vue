<template>
    <div class="big-wrapper flex-center-column-top">
        <h2 class="small-title" >What activity are you debating?</h2>

        <form action="" class="flex-center-column ">
            <p class="classic-text"> Activity name</p>
            <br>
            <input v-model="name" id="activity-input" class="text-input" type="text" >
            <input class="classic-input flex-center-column" v-on:click="addActivity()" type="button" value="ADD">
        </form>
        <div class="suggestions">
            <p class="classic-text"> Suggestions</p>
            <div class="single-activity-card" >
                <i class="fa-solid fa-plus icon-plus icon" v-on:click="addSuggestion('Beach')"></i>
                🏖️ Beach
                            
            </div>
            <div class="single-activity-card" >
                <i class="fa-solid fa-plus icon-plus icon" v-on:click="addSuggestion('Accommodation')"></i>
                🏠 Accommodation
                            
            </div>
            <div class="single-activity-card" >
                <i class="fa-solid fa-plus icon-plus icon" v-on:click="addSuggestion('Breakfast')"></i>
                🍳 Breakfast
                            
            </div>
            <div class="single-activity-card" >
                <i class="fa-solid fa-plus icon-plus icon" v-on:click="addSuggestion('Dinner')"></i>
                🍽️ Dinner
                            
            </div>
        </div>
        <div class="suggestions" >
            <p class="classic-text">Activities</p>
            
            <div class="single-activity-card" v-for="activity in activities" >
                <i class="fa-solid fa-x icon-x icon" v-on:click="removeAcivity(activity)"></i>
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
            activities: [],
            name: ''
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
