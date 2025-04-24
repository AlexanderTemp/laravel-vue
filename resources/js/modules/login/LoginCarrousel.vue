<template>
  <div class="embla bg-foreground text-background h-full rounded-md" ref="emblaRef">
    <div class="embla__container">
      <div class="embla__slide">Slide 1</div>
      <div class="embla__slide">Slide 2</div>
      <div class="embla__slide">Slide 3</div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { EmblaOptionsType } from 'embla-carousel'
import Autoplay from 'embla-carousel-autoplay'
import emblaCarouselVue from 'embla-carousel-vue'
import { Slot } from 'vue'

const { options } = defineProps<{
  options?: EmblaOptionsType
  slides: Slot[]
}>()

const [emblaRef] = emblaCarouselVue(options, [Autoplay()])
</script>

<style lang="css" scoped>
.embla {
  overflow: hidden;
}
.embla__container {
  display: flex;
}
.embla__slide {
  flex: 0 0 100%;
  min-width: 0;
}
</style>
