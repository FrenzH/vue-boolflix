<template>

    <div>
        
        <div class="moviesContainer">
            <cardFilmComponent v-for="movie in movies" :key="movie.key" :movies='movie'/>

        </div>
        

    </div>
    
    
    
  
</template>

<script>

import cardFilmComponent from '@/components/cardFilmComponent.vue';

export default {
    name: 'mainComponent',
    props:{
        movies: Array
    },
   
    


  
  components:{
    cardFilmComponent,
   
 }
}

</script>

<style lang="scss" scoped>
    .moviesContainer{
        display: flex;
        flex-wrap: wrap;
    }

</style>