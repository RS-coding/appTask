<template>
    <div class="container-tasks">
        <div  v-for="task in tasks" :key="task.id">
        <Task @showModal="$emit('showModal',task.id)" :task="task"/>
  </div>
    </div>
  
</template>

<script>

import Task from './Task.vue'


export default {
    components:{Task},
    name: 'Tasks',
    props:{
        tasks:Array,
    }
   
};
</script>

<style>
    .container-tasks{
        margin-top:20px;
    }
</style>
