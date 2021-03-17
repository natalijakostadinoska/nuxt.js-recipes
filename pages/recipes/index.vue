<template>
  <section class="recipes">
    <Recipe
      v-for="recipe in recepies"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :id="recipe.id"
      :previewText="recipe.previewText"
    />
  </section>
</template>

<script>
import Recipe from '@/components/Recipe'
export default {
    components: {
        Recipe
    },
    asyncData () {
        return new Promise((resolve, reject) => {
        setTimeout(() => {
        resolve({
            recepies: [
                {
                    id: '1',
                    title: 'Delicious Pasta',
                    previewText: 'Awesome Pasta!',
                    thumbnail: 'https://hips.hearstapps.com/delish/assets/17/36/1504715566-delish-fettuccine-alfredo.jpg'
                },
                {
                    id: '2',
                    title: 'Delicious Avocado Toast',
                    previewText: 'Very Tasty!!!',
                    thumbnail: 'https://eluxemagazine.com/wp-content/uploads/2017/05/avocado-recipes.jpg'
                  }
               ]
             })
         }, 1500)
       })
      }
};
</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row;
  justify-content: center;
  align-items: center;
}
</style>
