<template>
  <q-page padding>
    <!-- content -->
    <p v-text="msghtml"></p>
    {{ msghtml }}
    {{ msg }}
    <p v-text="msg"></p>

    <p>
      <template v-for="item in days" :key="item">
        <button v-if="item == 'Ponedjeljak'">
          {{ item }}
        </button>
        <button v-else>
          {{ item }}
        </button>
      </template>
    </p>

    <a :href="link.url" :target="link.target"> {{ link.text }} </a>
    <q-input v-model="input" label="Unesi ime"></q-input>
  </q-page>
</template>

<script setup>
import { ref } from 'vue';

const msg = 'Pozdrav';
const msghtml = 'Pozdrav2';
const days = ['Ponedjeljak', 'Utorak', 'Srijeda'];
const link = {
  url: 'http://www.google.com',
  target: '_blank',
  text: 'Google',
};
const input = ref('');
input.value = 'Pero';
</script>