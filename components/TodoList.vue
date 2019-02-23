<template>
	<div id = 'todolist'>
		<div class = 'todo'  v-for = "todo in todos" :key="todo.id">
			<input v-on:change = "todo.completed = !todo.completed" type = 'checkbox'/>
			<li v-bind:class = "{'isComplete':todo.completed}">{{todo.task}}</li>
			<button @click="$emit('del-todo', todo.id)"><span class="far fa-trash-alt fa-lg" ></span></button>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'TodoList',
		props: ['todos'],
	}
	
</script>

<style scoped>
	#todolist{
		width: 70%;
		margin-top: 40px;
		align-self: center;	
	}
	.todo{
		display: flex;
		align-items: center;
		box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
		margin-top: 10px;
		margin-bottom: 10px;
		padding: 10px;
		color: white;
		background: #07d2cd;
		text-shadow:  0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
		height: 12vh;
	}
	li{
		list-style-type: none;
		margin-left: 20px;
		font-weight: bolder;
		flex: 1;
	}
	.isComplete{
		text-decoration: line-through;
		opacity: 0.5;
	}
	button{
		float: right;
		background: none;
		border: none;
	}
	span{
		color: #ff4757;
	}
</style>