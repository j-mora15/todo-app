<template>
  <v-container class="lista">
    <TodoCard v-for="(item, index) in todos" :key="index" :info="item" />
  </v-container>
</template>

<script>
export default {
  name: 'FavoritesTodos',

  components: {
    TodoCard: () => import('../TodoCard/TodoCard.vue')
  },

  computed: {
    todos() {
      return this.$store.getters.favoriteTodos
    }
  }
}
</script>

<style lang="sass" scoped>
.lista
  margin-top: 166px

.card
  margin-top: 10px

@media screen and (max-width: 500px)
  .lista
    margin-top: 207px

@media screen and (max-width: 355px)
  .lista
    margin-top: 244px
</style>
