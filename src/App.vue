<template>
  <div id="app">

    <headerComponent @search="searchText" />
    <mainComponent :movies="movies" />

    
  </div>
</template>

<script>


import mainComponent from '@/components/mainComponent.vue';
import headerComponent from '@/components/headerComponent.vue';
import {apiKey} from '@/env';

import axios from 'axios';



export default {
  name: 'App',
  data(){
        return{
            
            movies:[],
        }
  },
  
  methods:{
   
    searchText(searchText){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${searchText}`)
      .then((response)=>{
        console.log(response);
        this.movies=response.data.results;
        console.log(this.movies)
      })
      
    },
    
  },
  


  
 
  
 
  components: {
    mainComponent,
    headerComponent,
    
 }
}

</script>

<style lang="scss">

</style>
