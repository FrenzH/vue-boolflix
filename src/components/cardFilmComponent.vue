<template>
    <div class="MoviesCards">
        <div class="description">

          <p>Title:{{movies.title}}</p>
        
          <p>Original title:{{movies.original_title}}</p>
          <p>Language:<flagsComponent :language='movies.original_language'/></p>
          <p>Vote:<starsComponent :vote='movies.vote_average'/></p>
          
          <p class="overview">Description:{{movies.overview}}</p>

          
          
        </div>
        <div class="cover">
            <coverComponent :URLimage='movies.poster_path' />

        </div>
        
    </div>
  
</template>

<script>
import flagsComponent from '@/components/flagsComponent.vue';    
import coverComponent from '@/components/coverComponent.vue';
import starsComponent from '@/components/starsComponent.vue';
export default {
    name:'cardFilmComponent',
    props:{
        movies: Array
    },
    data(){
        return{
            
        }
    },
 
    
    components:{
        flagsComponent,
        coverComponent,
        starsComponent
    }


}
</script>

<style lang="scss" scoped>
    .MoviesCards{
        
        margin: 10px;
        width: calc(100%/5);
        position: relative;
        height: 350px;
        font-size: 0.8rem;
        cursor: pointer;
        
        .overview{
            max-height: 90px;
            max-width: 50%;
            overflow-y: scroll;
            overflow-x: hidden;
            -ms-overflow-style: none;  
             scrollbar-width: none;
             
            
        }
        .overview::-webkit-scrollbar {
            display: none;
         }
         .cover {
            z-index: 3;
            position: absolute;
            
            height: 100%;
            width:100%;


         }

         
        
         
    }
   
    
    
    .description{
        
        position: absolute;
            height: 100%;
            width: 100%;   
            z-index: 2;
            background-color: #292828;
            opacity: 90%;
             
            
        
           

    }
    .MoviesCards:hover{
        .cover{
            z-index:1;
         }
    }
    .description p{
        padding: 5px;
        max-width: 170px;
    }
    

</style>