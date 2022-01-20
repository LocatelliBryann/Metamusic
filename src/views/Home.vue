<template>
  <v-container class="pa-8 white" fluid>
    <h1 class="h1">Artistas</h1>
    <v-form>
      <v-text-field label="Nova banda/música" v-model="novaTarefa" @keydown.enter="adicionar">
        <v-icon slot="append" @click="adicionar"> mdi-send</v-icon>
      </v-text-field>
    </v-form>
    <v-divider></v-divider>
    <v-list class="white">
      <v-list-item-group>
        <v-list-item v-for="tarefa of tarefas" :key="tarefa.id">
          {{tarefa.titulo}}
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-container>
</template>

<script>

</script>

<style>

</style>