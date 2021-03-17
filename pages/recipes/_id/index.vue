<template>
  <div class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title" />
    </div>
    <p>{{ recipe.descriptionText }}</p>
  </div>
</template>

<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
</style>

<script>
export default {
    asyncData (context) {
        return new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve({
                recipe: [
                  {
                    id: '1',
                    title: 'Delicious Pasta',
                    previewText: 'Awesome Pasta!',
                    descriptionText: 'Delicious meal',
                    thumbnail: 'https://hips.hearstapps.com/delish/assets/17/36/1504715566-delish-fettuccine-alfredo.jpg'
                },
                {
                    id: '2',
                    title: 'Delicious Avocado Toast',
                    previewText: 'Very Tasty!!!',
                    descriptionText: 'Delicious meal',
                    thumbnail: 'https://eluxemagazine.com/wp-content/uploads/2017/05/avocado-recipes.jpg'
                  }
               ].find(el => el.id === context.params.id)
            })
        }, 1500)
        })
    }
}
</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}

.recipe-image {
  width: 100%;
}
</style>
