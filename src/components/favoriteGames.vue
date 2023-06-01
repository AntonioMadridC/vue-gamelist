<template>
  <table class="table table-dark table-striped">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Juego</th>
        <th scope="col">Eliminar juego de tu lista</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(game, index) in games" :key="game">
        <th scope="row">{{ index + 1 }}</th>
        <td>{{ game }}</td>
        <td>
          <button class="btn btn-danger" @click="remove(index)">
            Eliminar
          </button>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "favorite-games",
  props: {
    games: {
      type: Array,
      required: true,
    },
  },
  data: function () {
    return {};
  },
  // computed: {},
  methods: {
    remove(index) {
      this.$emit("remove", index);
    },
  },
  // watch: {},
  // components: {},
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  // -- End Lifecycle Methods
};
</script>

<style scoped>
</style>