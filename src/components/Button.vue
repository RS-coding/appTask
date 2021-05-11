<template>
  <input class="btn" :style="{backgroundColor: bgcolor,color:color}" type="submit" value="Save task">
</template>

<script>
export default {
  name: 'Button',
  props:{
      bgcolor:String,
      color:String
  }
};
</script>

<style>


</style>
