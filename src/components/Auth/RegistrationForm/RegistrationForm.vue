<script setup>
import IInput from '@/components/IInput/IInput.vue';

</script>

<template>
  <form class="max-w-[500px] w-full bg-white p-10 rounded-2xl">
    <IInput class="mb-4" label="Повне ім’я" />
    <IInput class="mb-4" label="Електронна пошта" placeholder="email@gmail.com" />
    <IInput class="mb-4" label="Пароль" type="password" />
  </form>
</template>
