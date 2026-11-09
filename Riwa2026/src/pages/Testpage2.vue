<template>
  <q-page padding>
    <q-input color="purple-12" v-model="text" label="Unesi ime"> </q-input>
    <q-btn @click="DodajIme()">Napiši</q-btn>
    <p v-for="ime in kolege" :key="ime" v-show="ime != 'Ivan'">
      {{ ime }}
    </p>

    <!-- QBadge -->
    <div class="q-pa-md q-gutter-sm">
      <q-btn push color="white" text-color="primary" label="Add Mails" @click="addmail()">
        <q-badge color="orange" floating>{{ addmsg }}</q-badge>
      </q-btn>
      <q-btn dense color="purple" round icon="email" class="q-ml-md" @click="delMail()">
        <q-badge color="red" floating>{{ delmsg }}</q-badge>
      </q-btn>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const text = ref('')
const kolege = ref(['Ivan', 'Marko', 'Ana', 'Petra', 'Luka'])
const addmsg = ref(22)
const delmsg = ref(4)

function DodajIme() {
  kolege.value.push(text.value)
  console.log(text.value)
}

function addmail() {
  addmsg.value += 1
  console.log('add' + addmsg.value)
}

function delMail() {
  delmsg.value -= 1
  console.log('delete' + delmsg.value)
}
</script>