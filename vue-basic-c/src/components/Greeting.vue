<script setup>
import { defineProps } from 'vue'

// Definir las props recibidas del componente padre
const { nombreGreeting, tarea } = defineProps({
  nombreGreeting: String,
  tarea: String
})

// Función que genera el saludo en el componente hijo
const greetingMessage = () => {
  return `Hola, mi nombre es ${nombreGreeting} y soy tu ${tarea}.`
}
</script>

<template>
  <div class="greeting">
    <!-- Mostrar resultado del saludo en el componente hijo -->
    <p><strong>🎉 {{ greetingMessage() }} 🎉</strong></p>
  </div>
</template>

<style scoped>
.greeting {
  margin-top: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 30px;

}
</style>


  