<template>
  <div>
      <div class="task" :class="[task.completed ? 'completed' : '', 'task']">
          <div>
            <h3>{{task.text}}</h3>
            <p class="date-task">{{task.day}}</p>
          </div>
          <i @click="$emit('showModal', task.id)" class="fas fa-times"></i>
      </div>
  </div>
</template>

<script>
export default {
  name: 'task',
  props:{
      task:Object,
  },


};
</script>

<style>
    .task{
        margin:1rem 0;
        padding:1.4rem 2rem;
        background-color:#f4f4f4;
        box-shadow: 2px 1px 8px rgba(199, 199, 199, 0.74);
        cursor:pointer;

        display:flex;
        align-items:center;
        justify-content:space-between;
    }

    h3{
        font-weight:400;
        font-size:1rem;
    }

    .date-task{
        padding:.2rem 0;
        font-size:.8rem;
        color:rgb(146, 146, 146);
        font-style:italic;
        letter-spacing: .1rem;
    }

    .completed{
        border-left:10px solid rgb(90, 185, 90);
    }

    .fas{
        color:rgb(70, 70, 70);
        
    }
</style>
