<template>
    <div class="posts">
        <div>
            <input type="text" placeholder="Text here">
            <textarea name="" id="" cols="30" rows="10" ></textarea>
        </div>
        <button >Click display is where</button>
      <h1>Posts</h1>
    </div>

     
    <div>
       <button @click="what = true">show modals</button>
      <div v-if="what == true">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quibusdam similique, quia dolore delectus consectetur nobis earum omnis asperiores maxime molestias est error rem praesentium quas nihil quisquam cumque! Officiis, natus?
      </div>
      <button @click="what = false" >hide modals</button>
    </div>
  </template>
  
  <script setup>
        // import {useRoute} from "vue-router"
        // const route = useRoute(); // => this.$route
        // const routeDisplay = () => {
        //      alert(route.params.id)
        // } 
        import {ref} from 'vue'

        const what = ref(false);
  </script>

  
  <style>
  @media (min-width: 1024px) {
    .posts {
      min-height: 100vh;
      display: flex;
      align-items: center;
    }
  }
  </style>
  