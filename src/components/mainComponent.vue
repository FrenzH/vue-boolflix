<template>

    <div>
        <input type="text" v-model="searchText"><button @click="search"></button>
    </div>
  
</template>

<script>
import {apiKey} from '@/env';

import axios from 'axios';
export default {
    name: 'mainComponent',
    data(){
        return{
            searchText:''
        }
    },
    methods:{
    getAPI(searchText){
      
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${searchText}`)
        .then((response)=>{
        console.log(response);
      })
    },
    search(){
      this.getAPI(this.searchText);
    }


  }
}
</script>

<style lang="scss" scoped>

</style>