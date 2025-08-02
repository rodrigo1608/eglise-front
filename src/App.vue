<script setup>
import { ref } from 'vue'
import Aside from '@/layouts/Aside.vue'
import Header from './layouts/Header.vue'


const isAsideOpen = ref(false)
const toggleAside = () => isAsideOpen.value = !isAsideOpen.value
</script>

<template>
  <div class="flex flex-col sm:flex-row min-h-screen">
    <Header :toggle-aside="toggleAside" class="sm:hidden" />
    <Aside :is-aside-open="isAsideOpen" :toggle-aside="toggleAside" />
    <Header :toggle-aside="toggleAside" class="hidden sm:block" />

  </div>
</template>
