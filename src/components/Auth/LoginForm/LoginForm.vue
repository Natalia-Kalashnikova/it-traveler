<script setup>
import { reactive, watch } from 'vue';
import IInput from '@/components/IInput/IInput.vue';
import IButton from '@/components/IButton/IButton.vue';

const props = defineProps({
  isLoading: {
    default: false,
    type: Boolean
  }
})
const emit = defineEmits(['submit']);
const userData = reactive({
  email: '',
  password: '',
})

watch(
   userData,
   () => {
     console.log('user data changed')
   },
   { immediate: true }
 )
</script>

<template>
  <form @submit.prevent="emit('submit', userData)">
    <IInput class="mb-4" label="Електронна пошта" placeholder="email@gmail.com" v-model="userData.email" />
    <IInput class="mb-4" label="Пароль" type="password" v-model="userData.password" />
    <IButton class="mt-10 w-full" variant="gradient" type="submit" :is-loading="props.isLoading">
      Увійти
    </IButton>
  </form>
</template>
