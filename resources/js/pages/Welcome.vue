<script setup lang="ts">
import Button from '@/components/ui/button/Button.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
  <Head title="Bienvenido" />
  <div class="flex h-screen flex-col items-center justify-center">
    <p>hola mundo</p>
    <Button>Escalado</Button>
  </div>
</template>
