<template>
  <div id="app">

    <headerComponent @search="searchText" />
    
    <mainComponent :movies="movies" :tvSeries="tvSeries"/>

    
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
            tvSeries:[],
            popularMovies:[],
            popularTvSeries:[]
            
        }
  },
  created(){
      
      axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=${apiKey}`)
      .then((response)=>{
        console.log(response);
        this.movies=response.data.results;
        console.log(this.genres)
      })
      .catch(error=> {
          console.log(error.message)
        });
        axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=${apiKey}`)
      .then((response)=>{
        console.log(response);
        this.tvSeries=response.data.results;
        console.log(this.genres)
      })
      .catch(error=> {
          console.log(error.message)
        });

    },
  
  methods:{
   
    searchText(searchText){
      
      console.log(searchText);
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${searchText}`)
      .then((response)=>{
        console.log(response);
        this.movies=response.data.results;
        console.log(this.movies)
      })
      .catch(error=> {
          console.log(error.message)
        });
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${apiKey}&query=${searchText}`)
      .then((response)=>{
        console.log(response);
        this.tvSeries=response.data.results;
        console.log(this.tvSeries)
      })
      .catch(error=> {
          console.log(error.message)
        });
        
      
    },
    
  },

  
  


  
 
  
 
  components: {
    mainComponent,
    headerComponent,
   
    
 }
}

</script>

<style lang="scss">
   @import url('https://fonts.googleapis.com/css2?family=Comfortaa&display=swap');
  *{
    box-sizing: border-box;
    padding: 0;
    margin: 0;
    font-family: 'Comfortaa', cursive;
  }

</style>
