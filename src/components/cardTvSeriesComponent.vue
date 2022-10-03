<template>
  <div>
      <p>{{tvSeries.name}}</p>
        <p>{{tvSeries.original_name}}</p>
        <p><flagsComponent :language='tvSeries.original_language'/></p>
        <p>{{tvSeries.vote_average}}</p>
        <coverComponent :URLimage="tvSeries.poster_path" />
  </div>
</template>

<script>
  import flagsComponent from '@/components/flagsComponent.vue';  
  import coverComponent from '@/components/coverComponent.vue';
export default {
    name:'cardTvSeriesComponent',
    props:{
      tvSeries: Array
    },
    components:{
      flagsComponent,
      coverComponent
    }


}
</script>

<style lang="scss" scoped>

</style>