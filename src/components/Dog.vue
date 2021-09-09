<template>
    <div class="wrapper" v-if="url.length == 0"> 
        <button class="butt" @click="getDog">
            Get Dog
        </button>
    </div>
    <div class="wrapper" v-else>
        <img :src="url" />
        <div class="subtitle"> {{breed}} </div>
        <button class="butt" @click="getDog">
            Another One ?
        </button>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    name: "Dog",
    data() {
        return{
            url: "",
            breed: ""
        }
    },
    methods:{
        getDog(){
            axios({
                method: "GET",
                url: "https://dog.ceo/api/breeds/image/random"
            }).then(({data}) => {
                this.url = data.message
                console.log(this.url)
                this.breed = data.message.slice(30,data.message.lastIndexOf('/')).toUpperCase()
                console.log(this.breed)
            })
        }
    }
}
</script>

<style scoped>

.wrapper{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

img{
    height: 20rem;
    width: 25rem;
    border: solid white 3px;
}

.subtitle{
    font-size: 1.5rem;
    text-align: center;
    letter-spacing: 2px;
    padding: 1rem;
    font-family: 'Titillium Web', sans-serif;
    font-weight: 700;
}

.butt{
    margin-bottom: 1rem;
    padding: 0.3rem 0.5rem;
    font-size: 1rem;
    border: none;
    outline: none;
    color: white;
    border-radius: 5px;
    background-color: rgb(241, 86, 13);
    font-family: 'Titillium Web', sans-serif;
    letter-spacing: 0.7px;
}

.butt:hover{
    transform: scale(0.96,0.96);
}
</style>