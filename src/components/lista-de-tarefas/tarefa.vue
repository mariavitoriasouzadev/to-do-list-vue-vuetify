<template>
  <div>
    <v-list-item
      :class="{ 'pink accent-3': tarefa.concluido }"
      @click="tarefa.concluido = !tarefa.concluido"
    >
      <template v-slot:default="{}">
        <v-list-item-action>
          <v-checkbox
            :input-value="tarefa.concluido"
            color="black"
          ></v-checkbox>
        </v-list-item-action>

        <v-list-item-content>
          <v-list-item-title
            :class="{ 'text-decoration-line-through': tarefa.concluido }"
            >{{ tarefa.titulo }}</v-list-item-title
          >
        </v-list-item-content>

        <v-btn icon @click.stop="handleRemoveTarefa(tarefa.id)">
          <v-icon color="black">mdi-trash-can</v-icon>
        </v-btn>
      </template>
    </v-list-item>
    <v-divider></v-divider>
  </div>
</template>

<script>
export default {
  props: ["tarefa"],
  methods: {
    handleRemoveTarefa(id) {
      this.$store.commit("removeTarefa", id);
    },
  },
};
</script>

<style></style>
