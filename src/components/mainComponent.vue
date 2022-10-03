<template>

    <div>
        
        <div class="moviesContainer">
            <cardFilmComponent v-for="movie in movies" :key="movie.key" :movies='movie'/>
            <cardTvSeriesComponent v-for="tvSerie in tvSeries" :key="tvSerie.key" :tvSeries="tvSerie" />
        </div>
        

    </div>
    
    
    
  
</template>

<script>

import cardFilmComponent from '@/components/cardFilmComponent.vue';
import cardTvSeriesComponent from '@/components/cardTvSeriesComponent.vue';


export default {
    name: 'mainComponent',
    props:{
        movies: Array,
        tvSeries:Array
    },
   
    


  
  components:{
    cardFilmComponent,
    cardTvSeriesComponent
}
}

</script>

<style lang="scss" scoped>
    .moviesContainer{
        display: flex;
        flex-wrap: wrap;
    }

</style>