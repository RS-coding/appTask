<template>
        <form class="add-form"
              @submit.prevent="onSubmit">
            <div class="form-controls">
                <label for="task">Task </label>
                 <input v-model="text" id="task" type="text" name="text" placeholder="Add your task">
            </div>
           <div class="form-controls">
               <label for="">Date </label>
               <input v-model="day" type="text" name="day" id="date-task" placeholder="dd/mm/yy">
           </div>
           
            
            <Button bgcolor = "#333" color="white"/>
        </form>
</template>

<script>

import Button from './Button.vue'
export default {

  name: 'AddNewTask',
  components:{Button},
  data(){
      return{
          text:'',
          day:'',
          completed:false
      }
  },
  methods:{
      onSubmit(){
          if(!this.text){
              alert('Please add task')
              return
          }

          const newTask= {
              text:this.text,
              day:this.day,
              completed:this.completed,
              id: Math.floor(Math.random()* 1000000)
          }

          this.$emit('add-task', newTask)

          this.text =''
          this.day=''
          this.completed= false

      }
  }

};
</script>

<style scoped>
    .add-form{
        margin-top:3rem;
        display:flex;
        flex-direction:column;   
    }

    .form-controls{
        width:100%;
        display:flex;
        flex-direction:column;
        margin:1rem 0;
    }

    .form-controls label{
        padding-bottom:10px;
    }

    .form-controls input{
        padding:.7rem;
    }

   


    .btn{
        display:inline-block;
        border:none;
        padding:1rem 2rem;
        margin:5px 0;
        cursor:pointer;
        text-decoration:none;
        font-size:1rem;
        font-family:inherit;
        font-weight:600;
    }

 .btn:focus{
   outline:none;
 }

 .btn:active{
   transform:scale(.98);
 }

</style>
