<template>
	<section class="single-recipe">
		<h1>{{ recipe.title }}</h1>
		<div>
			<img :src="recipe.thumbnail" :alt="recipe.title">
		</div>
		<p>{{ recipe.descriptionText }}</p>
	</section>
</template>
<script>
	export default{
		asyncData(context){
			return new Promise((resolve,reject) => {
				setTimeout(() => {
					resolve({
						recipe: [
							{
								id: "1",
								title: "Delicious Pizza",
								descriptionText: "This is real relicious",
								thumbnail: "https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=1344671748,3471278999&fm=26&gp=0.jpg"
							},
							{
								id: "2",
								title: "Meiwei Hanbao",
								descriptionText: "This is real relicious",
								thumbnail: "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1536505529275&di=b0568179dbe33721bf58861f53fd3538&imgtype=0&src=http%3A%2F%2Fim1.tongbu.com%2Fappicon%2F316%2F316285.jpg%3F121003103102"
							}
						].find(el => el.id === context.params.id)
					})
				})
			})
		}
	}
</script>
<style scoped>
.single-recipe {
	display: flex;
	flex-flow: column;
	justify-content: center;
	align-items: center;
	text-align: center;
	padding: 80px;
}
</style>