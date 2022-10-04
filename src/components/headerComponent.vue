<template>
  <header>
    <div class="header-container">
      <div>
       <h1>BOOLFLIX</h1>
      </div>
    
      <div>
        
        <input type="text" v-model="searchText" @keyup.enter="$emit('search',searchText)" placeholder=" search">

        
       
        <button @click="$emit('search',searchText)">
          <font-awesome-icon :icon="['fa-solid','fa-magnifying-glass']" />
        </button>
      </div>

    </div>
    
  </header>
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
 

  header{
    
    
    background-color: black;
    padding: 10px;
    position: fixed;
    z-index: 100;
    width: 100%;
    height: 90px;
    opacity: 80%;
   
  
    .header-container{
      display: flex;
      justify-content:space-between;
      
      
      transform: translateY(50%);
    }
    
    
    h1{
      color: red;
      padding-left: 20px;
      
      
      
    }
    div div{
      display: flex;
     
      
    }
    
    div input:focus {
      outline: none;
      border-bottom-style: none;
    
    }
    div button :first-child:hover{
      font-size: 2rem;
    }

    div button :first-child{
      font-size: 1.6rem;
      color: white;
      vertical-align: middle;
      cursor: pointer;
    }
    button{
      background-color: black;
      
    }
    div input{
      height: 20px;
      align-self: center;
      border-radius: 8px;
       border-bottom-style: none;
       margin-right: 30px;
       padding: 10px;
      

    }
    
    

}

</style>