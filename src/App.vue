<script setup>
  import { ref } from 'vue'

  const tarefas = ref([
  {nome: 'Estudar', status: 'concluida'},
  {nome: 'Dormir', status: 'concluida'},
  {nome: 'Comer', status: 'pendente'},
  {nome: 'Trabalar', status: 'pendente'},
  ])
  const novaTarefa = ref('')

  // Concluir Tarefa

</script>

<template>
  <div class="container">
    <h1>Lista de Tarefas</h1>
    <ul>
      <li v-for="tarefa in tarefas" :key="tarefa" @click="tarefa.status = tarefa.status === 'concluida' ? 'pendente' : 'concluida'" :class="{concluida: tarefa.status == 'concluida'}">
      {{ tarefa.nome }}<button @click="tarefas.splice(tarefas.indexOf(tarefa), 1)">X</button>
    </li>
    </ul>
    <input type="text" v-model="novaTarefa">
    <button @click="tarefas.push({nome: novaTarefa, status: 'pendente'})">Adicionar</button>
  </div>
</template>

<style scoped>
li {
  cursor: pointer;
}
.concluida {
  color: lime
}
</style>
