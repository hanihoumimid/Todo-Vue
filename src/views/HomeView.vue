<template>
  <h1>Todo list</h1>
  <form @submit.prevent="addTask()">
    <label for="title">Titre de la tâche</label> &nbsp; &nbsp;
    <input type="text" name="title" v-model="form.title" />
    <br />
    <label>Etat : </label>
    <label>En cours</label>
    <input type="radio" value="en cours" v-model="form.etat" />
    <label>à faire</label>
    <input type="radio" value="à faire" v-model="form.etat" />

    &nbsp;&nbsp;<button>Ajouter une tâche</button>
  </form>

  <h1>Data</h1>

  <ul>
    <li v-for="x in list" :key="x.title">{{ x.title }} : {{ x.etat }}</li>
  </ul>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({
  title: '',
  etat: '',
})

const list = ref([])

const addTask = () => {
  list.value.push(form.value)

  form.value.title = ''
  form.value.title = ''
}
</script>
