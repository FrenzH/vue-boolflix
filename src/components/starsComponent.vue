<template>
  <div>
    <font-awesome-icon v-for="index in max" :key="index" 
        :icon="[
            index <= stars() ? 'fa-solid' : 'fa-regular',
            'fa-star'
        ]" />
  </div>
</template>

<script>

export default {
    name:'starsComponent',
    data(){
        return{
            max:5

        }
    },
    props:{
        vote:Number
    },
    methods:{

        stars(){
            let vote = this.vote;
            if(vote<2){
                vote=2;
                return Math.ceil(vote / 10 * this.max);
            }
            
           else return Math.ceil(this.vote / 10 * this.max);
            
        }

    }

}
</script>

<style>

</style>