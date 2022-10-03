<template>
  <div>
    <img :src="getImageUrl" :alt="cover">
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
            return 'https://image.tmdb.org/t/p/w185' + this.URLimage;

        }
    }

}
</script>

<style lang="scss" scoped>

</style>