<script>
import RecipeCard from '@/components/layout/recipe/card'

export default {
  components: {
    RecipeCard
  },
  mounted () {
    this.$store.dispatch('fetchFoods')
  },
  computed: {
    latestFoodIds: function () {
      return this.$store.getters.latestFoodIds
    }
  }
}
</script>

<template>
  <div id="explore" class="page">
    <RecipeCard
      v-for="id in latestFoodIds" :key="id"
      :recipeId=id
    />
  </div>
</template>

<style lang="scss">
#explore {
  display: grid;
  grid-template-columns: repeat(auto-fit, 28rem);
  grid-template-rows: auto;
  grid-gap: 1rem;
  justify-content: center;
}
</style>
