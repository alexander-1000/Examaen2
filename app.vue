<template>
    <div id="app">
      <SideMenu :isMenuOpen="isMenuOpen" @toggleMenu="toggleMenu" @navigate="changeView"/>
      <div class="content-area">
        <component :is="currentView" />
        <button @click="toggleMenu">Mostrar/Ocultar Menú</button>
      </div>
    </div>
  </template>
  
  <script>
  import SideMenu from './components/SideMenu.vue'
  
  export default {
    components: {
      SideMenu
    },
    data() {
      return {
        currentView: 'Home',
        isMenuOpen: false
      }
    },
    methods: {
      changeView(view) {
        this.currentView = view;
        this.toggleMenu();
      },
      toggleMenu() {
        this.isMenuOpen = !this.isMenuOpen;
      }
    }
  }
  </script>