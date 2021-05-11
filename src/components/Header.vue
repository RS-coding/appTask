<template>
    <div class="container-header">
             <h1>App Tasks</h1>
             <ButtonIcon 
             @toggleAddTask="$emit('toggleAddTask')"
             color='rgb(126, 198, 217)'/>
    </div>
</template>

<script>
import ButtonIcon from './Button_icon.vue'
export default {
  name: 'Header',
    components:{ButtonIcon}
};
</script>

<style scoped>
.container-header{
    width:100%;
    height:5rem;
     display:flex;
    flex-direction:row;
    justify-content: space-between;
    align-items:center;
}

</style>
