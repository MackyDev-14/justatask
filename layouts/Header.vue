<template>
	<header id = "header">
		<h1>Just a Task</h1>
	</header>
</template>

<script>
	export default{
		name: 'Header'
	}
	
</script>

<style scoped>
	#header{
		display: flex;
		height: 60px;
		background: #06adff;
		align-items: center;
		justify-content: center;
		padding-top:40px;
		padding-bottom: 40px;
		position: fixed;
		width: 100vw;
		top:0;
		box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
	}
	h1{
		color: white;
		font-size: 50px
	}
</style>