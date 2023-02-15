<script setup>
import { ref } from "@vue/reactivity";
import { onMounted, watch } from "@vue/runtime-core";

    const todo =ref([]);
    const title = ref("");
    const todo_title = ref("")
    const todo_category = ref("")

    watch(title ,(val)=>{
      localStorage.setItem('title', val)
    })

    onMounted(() => {
      title.value = localStorage.getItem('title');
      todo.value = JSON.parse(localStorage.getItem('todo')) || []
    })
    console.log(todo);
    const addTodo = (data) => {
        if(todo_title.value.trim() === '' || todo_category.value.trim() === null){
          alert('Bạn không được bỏ trống!');
        }else{
          todo.value.push({
            content:  todo_title.value,
            category: todo_category.value
          })
        }
    }

    watch(todo, val=>{
      localStorage.setItem('todo', JSON.stringify(val))
    },{deep: true});

    const removeTodo = () => {
      
    }

</script>
<template>
  <div class="todo_main">
  <div class="about">
    <input class="title" type="text" name="" id="" v-model="title" placeholder="TEXT HERE">
  </div>
  <div class="list_main">
    <h2 class="">Add somethink to day</h2>

    <form @submit.prevent="addTodo">
       <label for="">Do somethink</label> 
       <input type="text" name="" id="" v-model="todo_title"  placeholder="Text here do somethink">

       <label for="">Category</label>
       <input type="text" name="" id="" v-model="todo_category" placeholder="Text here category for work">
      
       <button class="list_button" type="submit">Submit</button>
    </form>
  </div>

  <div class="new_todo">
    <div v-for="(item, index) in todo" class="alone_new" v-bind:key="index">
    <div class="cate">{{ item.category }}</div>
    <span>{{ item.content }}</span>
      
      <button class="" @click="removeTodo">Delete</button>
  </div>
</div>
</div>
</template>

<style>
@media (min-width: 365px) {
  .todo_main {
    min-height: 100vh;
    width: 100%;
    /* background: rgb(232, 225, 225); */
    margin: 32px 0px 32px 0px;
  }
  .about .title{
    border: none;
    width: 130px;
    height: 30px;
    font-size: larger;
    font-weight: bold;
    color: blueviolet;
  }
  .todo_main form input{
    width: 100%;
    border-radius: 8px;
    height: 30px;
    border: none;

  }
  
  .todo_main .list_main h2{
    color: royalblue;
    font-weight: bold;
    text-align: center;
  }
  .todo_main form label{
    font-weight: bold;
  }
  .todo_main form button{
    width: 150px;
    text-align: center;
    margin: 0 auto;
    justify-content: center;
    display: flex;
    margin-top: 12px;
    font-weight: bold;
    background: orchid;
    color: aliceblue;
    height: 30px;
    line-height: 30px;
    border-radius: 8px;
    border: none;
  }
  .todo_main form{
    width: 100%;
  }
  .new_todo{
    border-top:2px solid  red;
    margin:32px 0 ;
    display: flex;
    flex-direction: column;
    gap: 12px;
    padding: 2px;
    padding-top: 12px;
    
  }
  .new_todo button{
    width: 60px;
    height: 25px;
    background: orange;
    color: #f0e9e9;
    font-weight: bold;
    border-radius: 8px;
    border: none;
  }
  .new_todo .cate{
    padding: 2px;
    border-radius:10px ;
    background: purple;
    color: #f0e9e9;
    font-weight: bold;
  }
  .alone_new{
    display: flex; 
    gap: 12px;
    justify-content: space-between;
    padding:8px;
    background: rgb(253, 253, 161);
    border-radius: 12px;
  }
}
</style>
