<script setup>
const props = defineProps({
  name: String,
  img: String,
  items: Array
})
</script>

<template>
  <nav class="navegador">
    <img :src="img" alt="Logo" />
    <ul class="enlaces">
      <li v-for="(item, index) in items" :key="index">
        <a href="">{{ item }}</a>
      </li>
    </ul>
  </nav>
</template>



<style scoped>
.navegador {
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
  margin-left: 30px;
  margin-right: 30px;
}


ul {
    list-style: none; /*para quitar puntos de ul del navegador*/
    display: flex;
    flex-direction: row;
    gap: 1rem; /*espacio entre los boxes*/

}

a {
    text-decoration: none; /*para quitar la linea de los links*/
    color: black;
}
</style>
