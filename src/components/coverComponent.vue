<template>
  <div class="img-container">
    <img :src="getImageUrl"  @error="setUnavailablePoster($event)">
  </div>

</template>

<script>
export default {
    name:'coverComponent',
    props:{
        URLimage:String

    },
    computed:{
        getImageUrl(){
            return 'https://image.tmdb.org/t/p/w300' + this.URLimage;

        }
    },
    methods: {
        setUnavailablePoster(event){
            event.target.src = 'https://via.placeholder.com/300x450'
        }
    }

}
</script>

<style lang="scss" scoped>
  .img-container{
    width: 100%;
    
  }
  img{
    width: 100%;
  }

</style>