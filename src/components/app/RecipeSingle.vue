<template>
  <div class="recipe-single">
    <h2>{{ currentRecipeObj.name }}</h2>
    <p>Description {{ currentRecipeObj.description }}</p>
    <ul>
      <li
        v-for="(value, key, index) in currentRecipeObj.ingredients"
        :key="key"
      >
        {{ index }}. {{ key.toUpperCase() }} : {{ value }}
      </li>
    </ul>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  computed: {
    ...mapState(['currentRecipeObj'])
  }
}
</script>

<style lang="scss">
.recipe-single {
  background: #f5f5f5;
  overflow-y: scroll;
  scrollbar-width: thin;
  min-height: 0;
  height: 100%;
  flex-basis: 80%;
  align-self: stretch;
}
</style>
