<template>
  <!-- {{arrOfValue}} -->
<table class="table">

  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col" v-for="(c,index) in cols" :key="index" >c{{c}}</th>
    </tr>

  </thead>

  <tbody>
    <tr v-for="(r,index) in rows" :key="index">
      <th scope="row">r{{r}}</th>
      <td scope="col" v-for="(c,index) in cols" :key="index">
        <input type="text" v-model="arrOfValue[r-1][c-1]">
        {{arrOfValue[r-1][c-1]}}
      </td>
    </tr>

  </tbody>

</table>
</template>

<script setup>
  import {reactive,computed,ref} from 'vue'
  let rows = 100;
  let cols = 15;
  let arrOfValue  = reactive([]);

  for (let i = 0; i < rows; i++) {
    arrOfValue[i] = [];
        for (let j = 0; j < cols; j++) {
          arrOfValue [i][j] = null;
        }
    }

</script>

<style scoped>
td,th{
  border:1px solid black;
  text-align: center;
  width:20px !important;
}
</style>