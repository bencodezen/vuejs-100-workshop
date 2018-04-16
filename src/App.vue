<template>
  	<div id="app">
		<h1 class="title">A Simple Calculator with <img class="vue-logo" src="./assets/logo.png" />.js</h1>
		<p class="subtitle">Built by You (<a href="#">@yourHandle)</a></p>
		<section style="display: flex; justify-content: center;">
			<Instructions />
		</section>
	</div>
</template>

<script>
import Instructions from './components/Instructions'

export default {
	name: 'App',
	components: {
		Instructions: Instructions
	}
}
</script>

<style>
html {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 30px;
}

.subtitle {
	margin-top: 5px;
	margin-bottom: 30px;
}

.title {
	display: flex;
	justify-content: center;
	align-items: center;
	margin-bottom: 0;
}

.vue-logo {
	width: 3rem;
	margin-left: 10px;
}
</style>
