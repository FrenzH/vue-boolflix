<template>
    <div class="MoviesCards">
        <p>{{movies.title}}</p>
        <p>{{movies.original_title}}</p>
        <p>{{movies.original_language}}</p>
        <p>{{movies.vote_average}}</p>
    </div>
  
</template>

<script>
export default {
    name:'cardFilmComponent',
    props:{
        movies: Array
    }


}
</script>

<style lang="scss" scoped>
    .MoviesCards{
        padding: 10px;
    }

</style>