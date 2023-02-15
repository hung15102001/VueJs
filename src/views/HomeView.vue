<!-- <script lang="ts">
</script> -->
<template>
  <div class="hpny">
    <h1> I love you 100 years

    </h1>

  </div>
 <!--  <main>
    <div class="main">
      <h3>{{ title }}</h3>
      <div  class="curcular">
      <button @click="decreated" class="increated">-</button>
      <h2 class="count">{{ counter }}</h2>
      <button @click="increated" class="increated">+</button>
    </div>

    <div class="table">
      <table border="1">
          <thead>
            <tr >
              <th>Stt</th>
              <th>Name</th>
              <th>Old</th>
              <th>Actions</th>
            </tr>
          </thead>
          <tbody>
              <tr v-for="item in users">
                <td>1</td>
                <td>{{ item.name }}</td>
                <td>{{ item.old }}</td>
                <td>
                    <p class="action">
                      <RouterLink to="/posts">Posts</RouterLink>
                    </p>
                </td>
              </tr>
          </tbody>
      </table>
      <input v-model="number()" type="text" /> 
      <button @click="number(1000000)">Click</button>
    </div>
    </div>
  </main> -->
</template> 

<script setup>
      import { ref } from 'vue'
      const users = [
        {
          name: "Hung",
        old: 22
        },
        {
          name: "Hung1",
        old: 22
        },
        {
          name: "Hung2",
        old: 22
        }
      ];
      console.log("value",users);
      const counter = ref(0)
      const title =  ref('My demo')
      const user = ref(users)
      const number = (num) => {
        const cv =  new Intl.NumberFormat('de-DE', {
          format: 'number',
    // style: 'currency',
    // currency: '',
    
      });
      const cv1 =  cv.format(num);
      const cv2 = cv1.repla
        console.log(cv.format(num));
      }
      const increated = () =>{
        counter.value++
      }
      const decreated = () =>{
        if(counter.value > 0){
            counter.value--
        }else{
          console.warn("hungdepzai");
            counter.value = 0
        }
      }
</script>

<style>
/* @media (min-width: 1024px) { */
  /* .main {
    min-height: 100vh;
    align-items: center;
  } */
  @import url('https://fonts.googleapis.com/css2?family=Abril+Fatface&family=Almendra+Display&display=swap');
  body{
    margin: 0;
    padding: 0;
    /* background: rgb(63,94,251);
background: radial-gradient(circle, rgba(63,94,251,1) 0%, rgba(97,90,225,1) 6%, rgba(142,84,191,1) 26%, rgba(252,70,107,1) 100%) !important;  */
font-family: 'Abril Fatface', cursive;
font-family: 'Almendra Display', cursive;
  }
  /* .curcular{
    display: flex;
    justify-content: center;
    gap:5px;
  }
  .main h3{
    margin: auto;
    text-align: center;
    font-weight: bold;
    margin: 10px 0 10px 0;
  }
  table{
    margin: auto;
    margin-top: 32px;
  }
  .action{
    border: 1px solid red;
    border-radius: 8px;
    padding: 2px;
  } */
  .hpny{
   width: 100%;
   height: 100vh;
   min-height: 100hv;
   text-align: center;
  }
  .hpny h1{
  display: flex;
   justify-content: center;
   bottom: -30%;
   left: 0%;
   color: white;
   font-weight: bold;
   font-size: 50px;
   text-shadow: 0 2px 2px #dfdfdf, 
      -2px 5px 1px #b8b8b8, 
      -4px 8px 0px #979797, 
      -6px 11px 0px #747474,
      -8px 14px 0px #565656,
      -10px 17px 0px #343434,
      -12px 20px 0px #171717,
      -14px 23px 0px #000;

  }
  /* .container{
    text-align: center;
    margin: auto;
  } */
/* } */
</style>

