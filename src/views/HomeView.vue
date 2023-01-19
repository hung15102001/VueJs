<!-- <script lang="ts">
</script> -->
<template>
  <main>
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
            </tr>
          </thead>
          <tbody>
              <tr v-for="item in users">
                <td>1</td>
                <td>{{ item.name }}</td>
                <td>{{ item.old }}</td>
              </tr>
          </tbody>
      </table>
      <!-- <input v-model="number()" type="text" /> -->
      <button @click="number(1000000)">Click</button>
    </div>
    </div>
  </main>
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
@media (min-width: 1024px) {
  .main {
    min-height: 100vh;
    align-items: center;
  }
  .curcular{
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
}
</style>

