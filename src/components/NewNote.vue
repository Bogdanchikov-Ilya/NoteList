<template>
	<div class="add__note">
		<label>Заголовок</label>
		<input type="text" placeholder="Заголовок" v-model="newNote.title">
		<label>Описание</label>
		<textarea placeholder="Описание" v-model="newNote.description"></textarea>
		<button @click="addNote">Добавить</button>
	</div>
</template>


<script>
export default {
	props: {
		newNote:{
			type: Object,
			required: true
		}
	},
	methods: {
		addNote(){
			this.$emit('addNote', this.newNote)
		}
	}
}
</script>



<style lang="scss" scoped>

.add__note{
	display: grid;
}

input{
	margin: auto;
	height:40px;
	border-radius: 13px;
	width: 60%;
	margin-bottom: 30px;
	border: 1px solid #a8a8a8;
	padding-left: 10px;
	font-size: 18px;
}
textarea{
	margin: auto;
	height:100px;
	width: 80%;
	margin-bottom: 30px;
	border: 1px solid #a8a8a8;
	border-radius: 13px;
	padding-left: 10px;
	padding-top: 5px;
	font-size: 17px;
}

label{
	font-size: 20px;
	margin-bottom: 10px;
	text-align: center;
}
button{
	width: 20%;
	height: 45px;
	margin: auto;
	background-color: #550fdc;
	color: white;
	border-radius: 19px;
	border: 1px solid #a8a8a8;
	font-size: 20px;
	transition: .1s linear;
	&:hover{
		transform: scale(1.03);
		transition: .1s linear;
	}
	&:active{
		border: 2px solid #343434;
	}
}

</style>
