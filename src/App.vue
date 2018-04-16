<template>
  	<div id="app">
		<h1 class="title">A Simple Calculator with <img class="vue-logo" src="./assets/logo.png" />.js</h1>
		<p class="subtitle">Built by {{ name }} (<a :href="twitter.url" :title="`${twitter.username}'s Twitter profile`">@{{ twitter.username }})</a></p>
		<section style="display: flex; justify-content: center;">
			<Calculator />
			<Instructions />
		</section>
	</div>
</template>

<script>
import Calculator from './components/Calculator'
import Instructions from './components/Instructions'

export default {
	name: 'App',
	data() {
		return {
			name: 'Ben Hong',
			twitter: {
				username: 'bencodezen',
				url: 'https://www.twitter.com/bencodezen'
			}
		}
	},
	components: {
		Calculator: Calculator,
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
