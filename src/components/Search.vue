<template>
	<div class="search__wrapper">
		<input type="text" class="search" placeholder="Поиск" v-model="search">
	</div>
</template>


<script>
export default {
    props: {
        value: {
            type: String,
			required: false
		}
	},
	data () {
		return {
            search: this.value
		}
	},
    watch: {
        search(val) {
            this.$emit('search', val);
        },
    },
	methods:{

	}
}
</script>


<style lang="scss" scoped>
	input{
		display: flex;
		width: 110%;
		margin-left: 20px;
		height:35px;
		border-radius: 13px;
		border: 1px solid #a8a8a8;
		margin-top: -3px;
		padding-left: 10px;
		font-size: 19px;
	}
</style>
