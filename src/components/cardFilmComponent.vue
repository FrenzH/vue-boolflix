<template>
    <div class="MoviesCards">
        <p>{{movies.title}}</p>
        <p>{{movies.original_title}}</p>
        <p><flagsComponent :movies='movies'/></p>
        <p>{{movies.vote_average}}</p>
    </div>
  
</template>

<script>
import flagsComponent from '@/components/flagsComponent.vue';    
export default {
    name:'cardFilmComponent',
    props:{
        movies: Array
    },
    components:{
        flagsComponent
    }


}
</script>

<style lang="scss" scoped>
    .MoviesCards{
        padding: 10px;
    }

</style>