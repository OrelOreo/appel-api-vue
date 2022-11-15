<template>

    <div class="container">
        <h1>Appel à une API</h1>
        <img v-bind:src="urlImg">
    </div>

</template>



<script>

import axios from 'axios'


export default {
    name:'ContenuPage',
    data(){
        return {
            urlImg: null
        }
    },
    mounted(){
        axios
        .get('https://api.thecatapi.com/v1/images/search')
        .then(reponse => {
            this.urlImg = reponse.data[0].url
        })
    }
}



</script>


<style>


</style>