<script setup lang="ts">
import Footer from '@/components/common/Footer.vue'
import { Card } from '@/components/ui/card'
import ThemeToggler from '@/components/utils/ThemeToggler.vue'
import LoginCarrousel from '@/modules/login/LoginCarrousel.vue'
import LoginForm from '@/modules/login/LoginForm.vue'
import Particles from '@/modules/login/Particles.vue'
import { Head } from '@inertiajs/vue3'
</script>

<template>
  <Head title="Login" />
  <Particles />
  <div class="relative flex min-h-[100dvh] flex-col justify-between">
    <div class="flex items-center justify-end px-3 pt-3 xl:px-12">
      <ThemeToggler />
    </div>
    <div class="grid flex-1 place-items-center">
      <div class="xl:w-[850px]">
        <Card class="!bg-transparent p-0 !backdrop-blur-sm xl:h-[550px]">
          <div class="grid h-full grid-cols-1 xl:grid-cols-2">
            <div class="p-2">
              <LoginCarrousel />
            </div>
            <LoginForm />
          </div>
        </Card>
      </div>
    </div>
    <Footer />
  </div>
</template>
