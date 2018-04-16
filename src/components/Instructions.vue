<template>
	<section class="instruction">
		<h1 class="instruction-title">Instructions</h1>
		<ol class="instruction-list">
			<li v-for="(instruction, index) in instructions"
				class="instruction-list-item"
				:key="index"
			>
				<input type="checkbox" :id="`instruction-${index}`">
					<label :for="`instruction-${index}`">{{ instruction }}</label>
				</input>
			</li>
		</ol>
	</section>
</template>

<script>
export default {
	name: 'Instructions',
	data() {
		return {
			instructions: [
				'Get up and running!',
				'Make the name a data property',
				'Swap in your handle with a data object that contains the username and the url',
				'Import Calculator component',
				'Generate number buttons',
				'Make numbers appear in equation on click',
				'Generate operations',
				'Make operations appear in equation on click',
				'Make the equal button evaluate the equation and update the value on the calculator',
				'Generate actions',
				'Integrate functionality for actions',
				'Attach a custom class of `is-wide` to the zero button'
			]
		}
	}
}
</script>

<style>
.instruction {
	padding-left: 20px;
}

.instruction-list {
	margin: 0;
	font-size: 1.2rem;
	text-align: left;
	max-width: 40ch;
}

.instruction-list-item {
	margin-bottom: 5px;
}

.instruction-title {
	margin-top: 0;
	margin-left: 1rem;
	font-size: 1.5rem;
	text-align: left;
}
</style>
