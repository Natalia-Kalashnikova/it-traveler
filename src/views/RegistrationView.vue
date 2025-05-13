<script setup>
import RegistrationForm from '@/components/Auth/RegistrationForm/RegistrationForm.vue';
import { registerUser } from '@/api/user/index.js';
import { useRouter } from 'vue-router'
import { useMutation } from '@/composables/useMutation.js';

const router = useRouter()
const { isLoading, error, mutation: handleRegisterUser } = useMutation({
  mutationFn: registerUser,
  onSuccess: ()=> router.replace('/map')
})

// const handleRegisterUser = async (userData) => {
//   isLoading.value = true;
//   try {
//     await registerUser(userData)
//     router.replace('/map')
//   } catch (error) {
//     console.error(error)
//   } finally {
//     isLoading.value = false
//   }
// }
</script>

<template>
  <RegistrationForm @submit="handleRegisterUser" :is-loading="isLoading" />
  <div v-if="error" class="text-red-500">{{ error.message }}</div>
</template>
