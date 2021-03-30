<template>
	<h2>{{message}}</h2>
</template>

<script>
	export default {
		props: {
		    message: {
		        type: String,
				required: true
			}
		}
	}
</script>

<style lang="scss" scoped>
	@import url('https://fonts.googleapis.com/css2?family=Varela+Round&display=swap');
	*{
		font-family: 'Varela Round', sans-serif;
	}
	h2{
		color: red;
		position: absolute;
		left:45%;
		top:320px;
		font-family: 'Varela Round', sans-serif !important;
	}
</style>
