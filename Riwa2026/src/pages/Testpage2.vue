<template>
  <q-page padding>
    <q-input color="purple-12" v-model="text" label="Tekst"> </q-input>
    <p>{{ text }}</p>
    <p v-for="ime in kolege" :key="ime" v-show="ime != 'Ivan'">
      {{ ime }}
    </p>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const text = ref('Pozdrav')

const kolege = ['Ivan', 'Marko', 'Ana', 'Petra', 'Luka']
</script>