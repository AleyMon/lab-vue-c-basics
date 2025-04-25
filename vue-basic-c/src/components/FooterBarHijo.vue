<script setup>
const props = defineProps({  //Una prop por grupo de Datos (direccion y columnas de li. El valor se pasa en padre )
  address: {
    type: Array, 
    required: true
  },
  sections: {
    type: Array,
    required: true
  }
})
</script>

<template>
<footer>
  <div class="logo-footer">
    <p v-for="(line, i) in address" :key="i">{{ line }}</p>
  </div>

  <ul v-for="(section, i) in sections" :key="i"> <!--Itera sobre el array 'sections'; se genera un <ul> por cada sección (3 veces tal como se declara en padre)-->
    <li v-for="(link, j) in section.links" :key="j"> <!--Itera sobre 'links' dentro de cada sección; se genera un <li> por cada link-->
      <a :href="link.url">{{ link.label }}</a> <!--Accede a 'url' y 'label' dentro de cada objeto 'link'-->
    </li>
  </ul>
</footer>

</template>


<style scoped>
/* ---- FOOTER -----*/

footer{
    margin-top: 200px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

footer ul {
    display: flex;
    flex-direction: column;

}

footer p, a{
    color: var(--neutral-medium);
    text-decoration: none;
    font: var(--headline-regular)
}
</style>


