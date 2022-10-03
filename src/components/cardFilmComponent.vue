<template>
    <div class="MoviesCards">
        <p>{{movies.title}}</p>
        <font-awesome-icon :icon="['fa-solid','fa-star']" />
        <p>{{movies.original_title}}</p>
        <p><flagsComponent :language='movies.original_language'/></p>
        <p>{{movies.vote_average}}</p>
        <coverComponent :URLimage='movies.poster_path' />
    </div>
  
</template>

<script>
import flagsComponent from '@/components/flagsComponent.vue';    
import coverComponent from '@/components/coverComponent.vue';
export default {
    name:'cardFilmComponent',
    props:{
        movies: Array
    },
    components:{
        flagsComponent,
        coverComponent
    }


}
</script>

<style lang="scss" scoped>
    .MoviesCards{
        padding: 10px;
    }

</style>