<template>
    <div class="big-wrapper flex-center-column">
        <h2 class="small-title" >{{title}}</h2>
        <form v-if="state=='initial'" action="" class="flex-center-column ">
            <p class="classic-text"> Name</p>
            <br>
            <input v-model="name" class="text-input" type="text" >
            <p class="classic-text">Link</p>
            <br>
            <input v-model="url" class="text-input" type="text">
            <br>
            <p class="classic-text">Description</p>
            <br>
            <input v-model="text" class="text-input" type="text">
            <br>
            <p class="classic-text">Photo</p>
            <br>
            <input class="text-input" type="file">
            <br>
            <input class="classic-input" v-on:click="sentProposal()" type="button" value="Propose">
        </form>
        <div v-if="state=='check'" class="icon-check flex-center-column">✔️</div>
        <div v-if="state=='vote'" class="flex-center-column">
            <div  class="icon-check flex-center-column padding" v-on:click="upvote()" >⬆️</div>
            <div  class="icon-check flex-center-column padding" v-on:click="impartial()">🔛</div>
            <div  class="icon-x flex-center-column padding" v-on:click="downvote()" >⬇️</div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        data() {
            return {
                name: '',
                url:'',
                text:'',
                img: '',
                upvote:'',
                downvote:'',
                price:'',
                state:'vote',
                title:'Propose something for the actvity on screen'
            }
        },
        methods: {
            sentProposal: function(){
             this.title = "You proposed! Now wait for the others"
             this.state = "check"
            }
        }
    }
</script>

<style scoped>
    @import '../assets/main.css';
    .icon-x{
        padding: 5px;
        background-color: #EF476F;
        height: 80px;
        width: 80px;
        border-radius: 1000px;
        color: white;
        text-align: center;
        font-size: 30px;
    }
    .icon-check{
        padding: 5px;
        background-color: green;
        height: 80px;
        width: 80px;
        border-radius: 1000px;
        color: white;
        text-align: center;
        font-size: 30px;
    }
    .padding{
        margin: 10px;
    }

</style>
