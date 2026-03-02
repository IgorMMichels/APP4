<script setup>
  import { ref } from 'vue'
  const tarefas = ref([
    'Seminário Português',
    'Seminário Geografia',
    'Contador Vue',
    'Seminário Ed. Física'
  ])
  const novaTarefa = ref('')
</script>

<template>
  <div class="container">
    <h1>Lista de Tarefas</h1>
    <ul>
      <li v-for="tarefa in tarefas" :key="tarefa">
      {{ tarefa }}
    </li>
    </ul>
    <input type="text" v-model="novaTarefa">
    <div>

    <button @click="tarefas.push(novaTarefa)">Adicionar</button>
    </div>
  </div>
</template>

<style scoped>
</style>
