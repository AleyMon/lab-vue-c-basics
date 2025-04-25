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

<template>
<footer>
    <div class="logo-footer">
        <p>2972 Westheimer Rd. Santa Ana,</p>
        <p>Illinois 85486</p>
    </div>
    <ul class="">
        <li><a href="" class="">Team</a></li> <!--INCLUIR LINKS-->
        <li><a href="" class="">Press</a></li>
    </ul>
    <ul class="">
        <li><a href="" class="">Services</a></li>
        <li><a href="" class="">Projects</a></li> <!--INCLUIR LINKS-->
    </ul>
    <ul class="">
        <li><a href="" class="">About Us</a></li>
        <li><a href="" class="">Privacy Policy</a></li> <!--INCLUIR LINKS-->
    </ul>
</footer>
</template>

<style scoped>
/* ---- FOOTER -----*/

footer{
    margin-top: 700px;
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

