<template>
  <div>
    <img
       :src="getFlagsUrl(language)"
       :alt="language"
       
      >
  </div>
</template>

<script>
export default {
    name: 'flagsComponent',
    props:{
        language:String
    },
    methods:{
        getFlagsUrl(language){
            switch(language){
                case 'en':{
                    language = 'gb';
                    break;
                }
                case 'ja':{
                    language = 'jp'
                    break;
                }
            }
            return `https://flagcdn.com/16x12/${language}.png`;
        }
       

    }

}
</script>

<style lang="scss" scoped>

</style>