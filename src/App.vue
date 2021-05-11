<template>
 <div class="container">
   <Header @toggleAddTask="toggleAddTask" :showAddTask="showAddTask"/>
   
   <div v-if="showAddTask">
     <AddNewTask @add-task="addTask"/>
   </div>
   
   <Tasks @showModal="show" :tasks="tasks" />

  <div v-if="showModal">
   
   <Modal @backHome = "cancel"/>

  </div>
 </div>
</template>

<script>

import Header from './components/Header.vue'
import AddNewTask from './components/AddNewTask.vue'
import Tasks from './components/Tasks.vue'
import Modal from './components/Modal.vue'

export default {

  name: 'App',
  components:{Header,AddNewTask, Tasks, Modal},
  data(){
    return{
      tasks:[
        {text:'Going to the hairstyle', id:1 ,day:'13/05/2021', completed:true},
        {text:'talking to the boss', id:2, day:'17/05/2021',completed:true},
        {text:'water the plants', id:3, day:'19/05/2021',completed:false}
      ],
      showAddTask: false,
      showModal: false
    }
  },
  methods:{
    toggleAddTask(){
      this.showAddTask = !this.showAddTask
    },
    addTask(task){
      this.tasks = [...this.tasks, task]
    },
    show(){
      this.showModal= true
      
    },
    cancel(){
      this.showModal = false
    }
    

  }
  
 
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600&display=swap');

*,
*::before,
*::after{
  margin:0;
  padding:0;
  box-sizing: border-box;
}

body,html{
  min-height:100vh;
}

body{
  font-family: 'Montserrat', sans-serif;
  color:rgb(46, 46, 46);
  display:flex;
  justify-content:center;
  align-items:center;
}

 .container{
   display:flex;
   flex:1;
   flex-direction:column;
   min-height:50rem;
   margin:auto;
   padding:30px;
   min-width:30rem;

   background-color:rgba(235, 235, 235, 0.2);
   border:1px solid rgb(197, 197, 197);
   box-shadow: 5px 5px 20px rgb(160, 160, 160);
   border-radius:.5rem;
 }


 

 

</style>
