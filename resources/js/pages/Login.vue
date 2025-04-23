<script setup lang="ts">
import Footer from '@/components/common/Footer.vue';
import { Card } from '@/components/ui/card';
import { FormControl, FormField } from '@/components/ui/form';
import FormItem from '@/components/ui/form/FormItem.vue';
import FormLabel from '@/components/ui/form/FormLabel.vue';
import Input from '@/components/ui/input/Input.vue';
import LoginCarrousel from '@/modules/login/LoginCarrousel.vue';
import { Head } from '@inertiajs/vue3';
import { toTypedSchema } from '@vee-validate/zod';
import { useForm } from 'vee-validate';
import * as z from 'zod';

const formSchema = toTypedSchema(
  z.object({
    username: z.string().min(2).max(50),
  }),
);

const form = useForm({
  validationSchema: formSchema,
});

const onSubmit = form.handleSubmit((values) => {
  console.log('Form submitted', values);
});
</script>

<template>
  <Head title="Login" />
  <div class="flex min-h-[100dvh] flex-col justify-between">
    <div></div>
    <div class="grid flex-1 place-items-center">
      <div class="xl:w-[850px]">
        <Card class="p-0">
          <div class="grid grid-cols-1 xl:grid-cols-2">
            <div class="p-2">
              <LoginCarrousel />
            </div>
            <div class="px-6 py-4">
              <form @submit="onSubmit">
                <FormField v-slot="{ componentField }" name="username">
                  <FormItem>
                    <FormLabel> Username </FormLabel>
                    <FormControl>
                      <Input type="text" placeholder="shadcn" v-bind="componentField" />
                    </FormControl>
                    <FormMessage />
                  </FormItem>
                </FormField>
              </form>
            </div>
          </div>
        </Card>
      </div>
    </div>
    <Footer />
  </div>
</template>
