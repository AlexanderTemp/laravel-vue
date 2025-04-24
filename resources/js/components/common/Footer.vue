<template>
  <div class="border-accent flex flex-col items-center justify-between gap-1 border-t-1 px-3 py-4 xl:flex-row xl:gap-0 xl:px-12">
    <Logo />
    <div class="flex flex-col items-center gap-2 xl:flex-row xl:gap-4">
      <Button variant="link">Términos</Button>
      <Button variant="link">Privacidad</Button>
      <Button variant="link">Soporte</Button>
      <Button variant="link">Contacto</Button>
    </div>
    <p class="text-primary">©{{ ActualYear }} {{ APP.name }} v.{{ APP.version }}</p>
  </div>
</template>

<script setup lang="ts">
import { APP } from '@/lib/constants';
import Button from '../ui/button/Button.vue';
import Logo from './Logo.vue';

const ActualYear = new Date().getFullYear();
</script>
