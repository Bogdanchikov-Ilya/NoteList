<template>
	<div class="notes">
		<div class="note" v-for="(note, index) in notes" :key="index">

			<div class="note__title">
				<p>{{note.title}}</p>
				<button class="button__remove" @click="removeNote(index)">
					<svg height="13px" viewBox="0 0 329.26933 329" width="13px" xmlns="http://www.w3.org/2000/svg"><g fill="#f44336"><path d="m21.339844 329.398438c-5.460938 0-10.925782-2.089844-15.082032-6.25-8.34375-8.339844-8.34375-21.824219 0-30.164063l286.589844-286.59375c8.339844-8.339844 21.824219-8.339844 30.164063 0 8.34375 8.339844 8.34375 21.824219 0 30.164063l-286.589844 286.59375c-4.183594 4.179687-9.621094 6.25-15.082031 6.25zm0 0"/><path d="m307.929688 329.398438c-5.460938 0-10.921876-2.089844-15.082032-6.25l-286.589844-286.59375c-8.34375-8.339844-8.34375-21.824219 0-30.164063 8.339844-8.339844 21.820313-8.339844 30.164063 0l286.589844 286.59375c8.34375 8.339844 8.34375 21.824219 0 30.164063-4.160157 4.179687-9.621094 6.25-15.082031 6.25zm0 0"/></g></svg>
				</button>
			</div>
			<div class="note__description">
				<p>{{note.description}}</p>
			</div>
			<div class="note__date">
				<p>{{note.date}}</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	props: {
	    notes: {
	        type:Array,
			required: true
		}
	},
	methods: {
	    removeNote(index){
			console.log(index)
			this.$emit('remove', index)
		}
	}
}
</script>

<style lang="scss" scoped>

.notes{
	display: flex;
	justify-content: space-between;
	width: 80%;
	margin: auto;
	margin-top: 30px;
	align-items: center;
	flex-wrap: wrap;
}

.note{
	border: 1px solid #dbdbdb;
	background-color: white;
	width: 48%;
	text-align: unset;
	padding: 15px;
	margin-bottom: 20px;
}
.note__title{
	font-size: 21px;
	color: #550fdc;
	margin-bottom: 10px;
	display: flex;
	justify-content: space-between;
	align-items: center;
}

.note__description{
	font-size: 17px;
	margin-bottom: 10px;
}

.note__date{
	font-size: 11px;
	color: #b6b6b6;
}
.button__remove{
	background-color: white;
	border: none;
	outline: none;
	svg{
		background-color: white;
		g{
			fill: #b6b6b6;
			padding: 15px !important;
			&:hover{
				fill: #ec3c3c;
			}
		}
	}
}





</style>
