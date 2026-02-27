<script setup>
import sidebar from './components/sidebar.vue'
import navbar from './components/navbar.vue'
/*import navbar from './components/navbar.vue'*/
defineOptions({
  extends: sidebar
})
</script>

<template>
  <navbar/>
  <sidebar/>
</template>

