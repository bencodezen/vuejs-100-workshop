<template>
  <div id="app">
		<h1>Let's Build a Calculator with <img src="./assets/logo.png" width=50 /></h1>
		<Calculator />
	</div>
</template>

<script>
import Calculator from './components/Calculator'

export default {
	name: 'App',
	components: {
		Calculator: Calculator
	}
}
</script>

<style>
#app {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
</style>
