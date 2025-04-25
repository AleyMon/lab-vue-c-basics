<script setup>
import { reactive } from 'vue';

const EnlacesNav = reactive (['Premium', 'Discover', 'Help', 'Download'])

</script>

<template>
    <nav class="navegador">
      <img src="../assets/icons8-ver-js-48.png" alt="Logo" />
      <ul class="enlaces">
        <li v-for="(enlaces, index) in EnlacesNav" :key="index"><a href="">{{ enlaces }}</a></li>
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

