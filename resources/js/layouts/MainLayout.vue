<template>
  <slot />
  <ResponsiveChip v-show="APP.env === 'development'" />
</template>

<script setup lang="ts">
import ResponsiveChip from '@/components/utils/ResponsiveChip.vue';
import { APP } from '@/lib/constants';
</script>
