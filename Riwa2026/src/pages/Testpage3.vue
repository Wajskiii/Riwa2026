<template>
  <q-page padding>
    <!-- QBadge -->
    <div class="q-pa-md q-gutter-sm">
      <q-btn push color="white" text-color="primary" label="Unread Mails">
        <q-badge color="orange" floating>{{ readmsg }}</q-badge>
      </q-btn>
      <q-btn dense color="purple" round icon="email" class="q-ml-md">
        <q-badge color="red" floating>{{ delmsg }}</q-badge>
      </q-btn>
    </div>

    <!-- QCard -->
    <div class="q-pa-md row items-start q-gutter-md">
      <q-card
        v-for="poruka in msg"
        :key="poruka.title"
        class="my-card bg-secondary text-white"
      >
        <q-img v-if="showGif" :src="gif" />
        <q-card-section>
          <div class="text-h6">{{ poruka.title }}</div>
          <div class="text-subtitle2">by {{ poruka.author }}</div>
        </q-card-section>
        <q-card-section>
          {{ poruka.text }}
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat @click="openMsg()">Open</q-btn>
          <q-btn flat @click="deleteMsg()">Delete</q-btn>
        </q-card-actions>
      </q-card>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import gif from '../assets/5cuU-e.gif'

const readmsg = ref(22)
const delmsg = ref(4)
const showGif = ref(false)

const msg = [
  {
    title: 'Changing planet',
    author: 'John Doe',
    text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, ...'
  },
  {
    title: 'New planet',
    author: 'Johndoe',
    text: 'Lorem ipsum.'
  },
  {
    title: 'New update',
    author: 'Doe',
    text: 'Lorem.'
  }
]

function openMsg() {
  showGif.value = true
}

function deleteMsg() {
  showGif.value = false
}
</script>