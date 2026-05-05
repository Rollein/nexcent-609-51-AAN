<script setup>
import { RouterView } from 'vue-router'
import Vheader from '@/Components/Vheader.vue'
import Vfooter from '@/Components/Vfooter.vue'
</script>

<template>
  <Vheader/>
  <RouterView/>
  <Vfooter/>
</template>

<style scoped></style>
