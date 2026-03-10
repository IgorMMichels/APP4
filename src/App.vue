<script setup>
  import { ref } from 'vue'

  const tarefas = ref([
  {nome: 'Estudar', status: 'concluida'},
  {nome: 'Dormir', status: 'concluida'},
  {nome: 'Comer', status: 'pendente'},
  {nome: 'Trabalhar', status: 'pendente'},
  ])
  const novaTarefa = ref('')

  // Concluir Tarefa

</script>

<template>
  <div class="container">
    <h1>Lista de Tarefas</h1>
    <ul>
      <li v-for="tarefa in tarefas" :key="tarefa" @click="tarefa.status = tarefa.status === 'concluida' ? 'pendente' : 'concluida'" :class="{concluida: tarefa.status == 'concluida'}">
      {{ tarefa.nome }} <button @click="tarefas.splice(tarefas.indexOf(tarefa), 1)">Edit</button> <button @click="tarefas.splice(tarefas.indexOf(tarefa), 1)">Delete</button>
    </li>
    </ul>
    <input type="text" v-model="novaTarefa">
    <button @click="tarefas.push({nome: novaTarefa, status: 'pendente'})">Adicionar</button>
    <button @click="tarefas.sort(tarefas.nome.sort())">Ordenar Tarefas</button>
  </div>
</template>

<style scoped>
li {
  cursor: pointer;
}
.concluida {
  color: lime
}
.container {
  padding: 15px;
  height: 100%;
  background-color: #181222;
  border-radius: 15px;
}
</style>
