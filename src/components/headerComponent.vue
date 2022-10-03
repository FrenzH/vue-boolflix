<template>
  <div>
    <input type="text" v-model="searchText" @keyup.enter="$emit('search',searchText)"><button @click="$emit('search',searchText)"></button>

  </div>
</template>

<script>
export default {
    name: 'headerComponent',
    data(){
        return{
            searchText :''
        }
    }

}
</script>

<style lang="scss" scoped>

</style>