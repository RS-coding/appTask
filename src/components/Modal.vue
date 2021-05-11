<template>
  <div class="modal">
      <div class="container-modal">
          <h1>Are you sure?</h1>
          <div class="container-buttons">
              <button @click="filterArray()" class="btn-modal yes">yes</button>
              <button @click="$emit('backHome')" class="btn-modal cancel">cancel</button>
          </div> 
      </div>
      
  </div>
</template>

<script>

export default {
  name: 'Modal',
  props:{
      tasks:Array
  },
 
  
    
};
</script>

<style>
    .modal{
        position:absolute;
        top:0;
        left:0;
        background-color:#777777c0;
        width:100vw;
        height:100vh;

        display:flex;
        justify-content:center;
        align-items:center;

    }

    .container-modal{
        background-color:#fff;
        padding:2rem;
        min-width:25rem;
        height:15rem;

        display:flex;
        flex-direction:column;
        align-items:center;
        justify-content:space-around
    }

    .container-buttons{
        width:70%;
        display:flex;
        justify-content:space-around;
    }

    .btn-modal{
        padding: 1rem 2rem;
        border:none;
        outline:none;
        cursor:pointer;
    }

    .yes{
        background-color:rgb(126, 198, 217);
    }

    .cancel{
        background-color:rgb(226, 226, 226);
    }
</style>
