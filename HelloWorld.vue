<template>
<div class="container">
  <input v-model="hobi" placeholder="Masukkan hobi..."class="input-box"/>
  <button @click="toggleHobi" :disabled="hobi===''">
    {{ tampilkan ?'sembunyikan hobi':'tampilkan hobi' }}
  </button>;
  <p v-if="tampilkan">Hobi Saya Adalah {{ hobi }}</p>
  <p v-if="tampilkan"
    :class="{'text-green':hobi.length >5,'text-red': hobi.length <=5}">
  panjang hobi: {{ hobi.length }} karakter</p>

</div>
</template>
<script setup>
import { ref } from 'vue';
const hobi = ref('');
const tampilkan = ref('false');


const toggleHobi = () =>{
  tampilkan.value = !tampilkan.value;
};
</script>
<style>
.container{
  text-align: center;
  font-weight: bold;
  margin-top: 20px;
}
.input-box{
  padding: 8px;
  margin-bottom: 10px;
}
.text-green{
  color: green;
}
.text-red{
  color: red;
}
</style>




