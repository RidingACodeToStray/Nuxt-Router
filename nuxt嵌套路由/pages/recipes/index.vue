<template>
  <section class="recipes">
  	<Recipe 
  	  v-for="recipe in recipes"
  	  :key="recipe.id"
  	  :thumbnail="recipe.thumbnail"
  	  :title="recipe.title"
  	  :id="recipe.id"
  	  :previewText="recipe.previewText" />
  </section>
</template>

<script>
import Recipe from '@/components/Recipe';
export default {
	components:{
		Recipe
	},
	asyncData(){
		return new Promise((resolve,reject) => {
			setTimeout(() => {
				resolve({
					recipes: [
						{
							id: "1",
							title: "Delicious Pizza",
							previewText: "Awwsome Pizza",
							thumbnail: "https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=1344671748,3471278999&fm=26&gp=0.jpg"
						},
						{
							id: "2",
							title: "Meiwei Hanbao",
							previewText: "This is meiweide hanbao",
							thumbnail: "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1536505529275&di=b0568179dbe33721bf58861f53fd3538&imgtype=0&src=http%3A%2F%2Fim1.tongbu.com%2Fappicon%2F316%2F316285.jpg%3F121003103102"
						}
					]
				})
			})
		})
	}
}
</script>

<style scoped>
.recipes {
	display: flex;
	flex-flow: row wrap;
	justify-content: center;
	align-items: center;
}
</style>