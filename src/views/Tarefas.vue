<template>
  <div>
    <v-col cols="12">
      <v-text-field
        v-model="campoInput"
        label="Insira uma tarefa"
        outlined
        clearable
        @keyup.enter="handleAddTarefa"
      ></v-text-field>
    </v-col>
    <v-divider></v-divider>

    <v-list flat subheader>
      <v-list-item-group multiple active-class="">
        <div v-for="(tarefa, index) in $store.state.tarefas" :key="index">
          <tarefa :tarefa="tarefa" />
          <tarefa />
          <tarefa />
          <tarefa />
          <tarefa />
          <tarefa />
          <tarefa />
        </div>
      </v-list-item-group>
    </v-list>
  </div>
</template>

<script>
import tarefa from "../components/lista-de-tarefas/tarefa.vue";
export default {
  name: "Home",

  components: {
    tarefa,
  },
  data() {
    return {
      campoInput: null,
    };
  },
  methods: {
    handleAddTarefa() {
      this.$store.commit("adicionaTarefa", this.campoInput);
      this.campoInput = null;
    },
  },
};
</script>
