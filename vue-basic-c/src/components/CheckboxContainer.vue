<script setup>
import { ref } from 'vue'
import PostList from './PostList.vue'  // Importamos el componente PostList

const isChecked = ref(false)   // Para el checkbox "Sí"
const NotChecked = ref(false)  // Para el checkbox "Tal vez más tarde"

const handleCheckboxChange = () => {
  // Si ambos checkboxes están seleccionados, desmarcar uno de ellos
  if (isChecked.value && NotChecked.value) {
    // Logica para evitar que ambos estén seleccionados
    if (isChecked.value) {
      NotChecked.value = false
    } else {
      isChecked.value = false
    }
  }
}
</script>

<template>
  <div class="checkbox-container">
    <p>¿Quieres que te muestre algunas opciones?</p>
    
    <!-- Checkbox 1 -->
    <div class="checkboxuno">
      <input 
        type="checkbox" 
        v-model="isChecked" 
        :value="'Si'" 
        @change="handleCheckboxChange"   
      />
      <label :style="{ color: isChecked ? 'red' : 'black', fontWeight: isChecked ? 'bold' : 'normal' }">Sí</label>
    </div>
    
    <!-- Checkbox 2 -->
    <div class="checkboxdos">
      <input 
        type="checkbox" 
        v-model="NotChecked" 
        :value="'Tal vez mas tarde'" 
        @change="handleCheckboxChange" 
      />
      <label>Tal vez más tarde</label>
    </div>
  </div>

  <div class="texto">
    <p v-if="isChecked">Genial! Vamos allá</p>
    <p v-if="NotChecked">Estaré aquí para cuando me necesites 😀</p>
  </div>

  <!-- Aquí agregamos el componente PostList -->
  <PostList v-if="isChecked" />
</template>



<style scoped>
.checkbox-container {
  margin-bottom: 20px;
}

.texto {
  margin-top: 20px;
}
</style>


  <style scoped>
  .checkbox-container{
    display: flex;
    flex-direction: column;
    margin-top: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 15px;


  }

  input{
    flex-direction: row;
  }

.checkboxuno,
.checkboxdos {
  display: flex;
  gap: 15px; /* Espacio entre checkbox y label */
}

.texto{
  display: flex;
  justify-content: center;
  margin-top: 15px;
  font-size: 30px;
}
</style>
  