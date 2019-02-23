<template>
	<div id = "todoform">

		<input placeholder="New Task" v-model = "task" id = "taskinput" />

		<button class="btn" @click = "addTodo">Add</button>

	</div>	
</template>

<script>
	export default{
		name: 'TodoForm',
		data(){
			return{
				task: '',
			}
		},
		methods: {
			addTodo(){

				if(this.task === '') return;

				const newTodo = {
					id: Math.floor(Math.random()*1000),
					task: this.task,
					completed: false
				}
				this.task = '';
				this.$emit('add-todo', newTodo);
			},
		}
	}
</script>

<style scoped>
	*{
		font-size: 18px;
	}

	#todoform{
		position:fixed;
		display: flex;
		flex-direction: row;
		position: relative;
		align-items: center;
		justify-content: center;
	}
	.btn{
		border: none;
		background: #ff8100;
		color: white;
		height: 30px;
		margin-left: 10px;
	}
	#taskinput{
		border:none;
		border-bottom: 3px solid #06adff;
		padding: 8px;
	}

	:focus{
		outline: none
	}


</style>