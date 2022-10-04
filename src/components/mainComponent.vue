<template>

    <div>
        
        <div class="Container">
            <h1>MOVIES</h1>
            <div>
                <cardFilmComponent v-for="movie in movies" :key="movie.key" :movies='movie'/>

            </div>
            <h1>TVSERIES</h1>
            <div>
                <cardTvSeriesComponent v-for="tvSerie in tvSeries" :key="tvSerie.key" :tvSeries="tvSerie" />

            </div>
            
           
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
    .Container{
        
        
        background-color:#292828;
        padding-top: 120px;
        color: white;
        div{
            display: flex;
            flex-wrap: wrap;
            margin: auto;
            row-gap: 20px;
        }
        h1{
            padding: 30px;
            margin-bottom: 30px;
           
        }
        
    }

</style>