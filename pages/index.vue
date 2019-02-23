<template>
	<div id="index">
		<div id = "todoform">
			<TodoForm v-on:add-todo = "addTodo"/>
		</div>
			

		<TodoList v-bind:todos = 'todos' v-on:del-todo = "delTodo"/>
	</div>
</template>

<script>
	import TodoForm from '~/components/TodoForm.vue'
	import TodoList from '~/components/TodoList.vue'

	export default {
	  components: {
	    TodoForm,
	    TodoList
	  },
	  data: () => {
	  		return {
	  			todos: []
	  		}
	  },
	  methods: {
	  	delTodo(id){
	  		this.todos = this.todos.filter(todo => todo.id != id);
	  	},
	  	addTodo(newTodo){
	  		this.todos.push(newTodo)
	  	}
	  }
	}
</script>

<style>
 #index{
 	display: flex;
 	flex-direction: column;
 	justify-content: center;
 	margin-top: 100px;
 	width: 100%;
 	padding: 10px;
 }
 #todoform{
 	position: fixed;
 	top: 0;
 	margin-top: 50px;
 	align-self: center;
 }
</style>
