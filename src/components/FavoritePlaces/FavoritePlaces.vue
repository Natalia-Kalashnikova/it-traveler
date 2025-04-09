<script setup>
import FavoritePlace from '../FavoritePlace/FavoritePlace.vue';
import IButton from '../IButton/IButton.vue';
import { ref, reactive } from 'vue';

const counter = ref(0);
const user = ref({ name: 'Tom', age: '14' })
const superUser = reactive({ name: 'Super User', age: '1000' })
const { name, age } = superUser

const increment = () => {
  counter.value += 1;
}

const changeUserName = () => {
  user.value.name = 'Harry Potter'
}

const changeSuperUserName = () => {
  superUser.name = 'New Super User'
}
</script>

<template>
      <div class="px-6">
        <div class="text-gray"> User name: {{ user.name }}</div>
        <div class="text-gray"> Super user name: {{ name }}</div>
        <div class="text-gray mb-4">Додані маркери ({{ counter }})</div>
        <slot name="label"></slot>
        <slot name="list">
        <FavoritePlace v-for="n in 4" :key="n" />
        </slot>
        <slot></slot>
      <IButton class="w-full" @click="changeUserName">Change Name</IButton>
      <IButton class="w-full mt-2" @click="changeSuperUserName">Change Super User Name</IButton>
      <IButton class="w-full mt-10" @click="increment">Додати маркер</IButton>
    </div>
</template>
