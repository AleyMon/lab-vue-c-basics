<script setup>
import { ref } from 'vue'

import NavBar from './components/NavBar.vue'
import NavBarHijo from './components/NavBarHijo.vue'
import logo from './assets/logo.png'
import FooterBarHijo from './components/FooterBarHijo.vue'
import Greeting from './components/Greeting.vue'
import CheckboxContainer from './components/CheckboxContainer.vue'

// DEFINIR DATOS / VARIABLES

// Datos NavBar
const enlaces = ref(['Premium', 'Discover', 'Help', 'Download'])
const nombre = 'MiNavbar'

// Datos Footer
const footerAddress = [
  '2972 Westheimer Rd. Santa Ana,',
  'Illinois 85486'
]

const footerLinks = [
  {
    title: 'Company',
    links: [
      { label: 'Team', url: '/team' },
      { label: 'Press', url: '/press' }
    ]
  },
  {
    title: 'Services',
    links: [
      { label: 'Services', url: '/services' },
      { label: 'Projects', url: '/projects' }
    ]
  },
  {
    title: 'Info',
    links: [
      { label: 'About Us', url: '/about' },
      { label: 'Privacy Policy', url: '/privacy' }
    ]
  }
]

// Datos Greeting
const nombreGreeting = ref('Pepit@')
const tarea = ref('Asistente')
</script>

<template>
  <NavBarHijo :name="nombre" :img="logo" :items="enlaces" />
  <Greeting :nombreGreeting="nombreGreeting" :tarea="tarea" />
  <CheckboxContainer />
  <FooterBarHijo :address="footerAddress" :sections="footerLinks" />
</template>

<style scoped>
</style>
