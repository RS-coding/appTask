<template>
  <button @click="$emit('toggleAddTask')" :style="{ backgroundColor: color }" class="btn-add">
      <i class="fas fa-pencil-alt"></i>
  </button>
</template>

<script>
export default {
  name: 'Button',
  props:{
      color:String
  }
};
</script>

<style>
  .btn-add{
      border:none;
      padding:1rem;
      border-radius:50%;
      cursor:pointer;
  }

  .btn-add:active{
      transform: scale(.95);
      box-shadow:1px 1px 5px rgb(114, 114, 114);
  }

  .fas.fa-pencil-alt{
      font-size:1.5rem;
      color:white;
  }

</style>
