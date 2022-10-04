<template>
  <div class="TvSeriesCards">
    <div class="description">
        <p>Title:{{tvSeries.name}}</p>
        <p>Original title:{{tvSeries.original_name}}</p>
        <p>Language:<flagsComponent :language='tvSeries.original_language'/></p>
        <p>Vote:<starsComponent :vote='tvSeries.vote_average'/></p>
        <p class="overview">Description:{{tvSeries.overview}}</p>
        

    </div>
    <div class="cover">
      <coverComponent :URLimage="tvSeries.poster_path" />
    </div>
        
  </div>
</template>

<script>
  import flagsComponent from '@/components/flagsComponent.vue';  
  import coverComponent from '@/components/coverComponent.vue';
  import starsComponent from '@/components/starsComponent.vue';
export default {
    name:'cardTvSeriesComponent',
    props:{
      tvSeries: Array
    },
    components:{
      flagsComponent,
      coverComponent,
      starsComponent
    }


}
</script>

<style lang="scss" scoped>
  .TvSeriesCards{
        
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
    .TvSeriesCards:hover{
        .cover{
            z-index:1;
         }
    }
    .description p{
        padding: 5px;
        max-width: 170px;
    }

</style>