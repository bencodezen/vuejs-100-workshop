<template>
  <article class="calc">
    <section class="calc-panel">
      <p class="calc-total">
		  <!-- Render expression data here -->
	  </p>
			<div class="calc-btn-grid">
				<div class="calc-num-grid">
					<!-- Generate number buttons (i.e., 1, 2, 3 ... 0, .) -->
					<!-- Element: button -->
					<!-- Class: calc-btn -->
				</div>
				<div class="calc-other-grid">
					<!-- Generate action buttons (i.e., C, +/-, ^) -->
					<!-- Element: button -->
					<!-- Class: calc-btn -->
				</div>
				<div class="calc-operations-grid">
					<!-- Generate operations buttons (i.e., /, *, +, -, =) -->
					<!-- Element: button -->
					<!-- Class: calc-btn -->
				</div>
			</div>
    </section>
  </article>
</template>

<script>
export default {
	name: 'Calculator',
	data: {}
}
</script>

<style>
:root {
	--pale-blue: #ebf6fc;
	--dark-gray: #3a3a3a;
	--red: #ad5153;

	--purple: #554a58;
	--gray: #4a4a4a;
	--teal: #538881;

	--row-gutter: 20px;
}

.calc {
	display: grid;
}

.calc {
	display: flex;
	max-width: 320px;
	background-color: var(--dark-gray);
	box-sizing: border-box;
	overflow: hidden;
}

.calc-btn-grid {
	display: grid;
	grid-template-columns: 3fr 1fr;
	grid-template-areas:
		'other operations'
		'numbers operations';
}

.calc-operations-grid {
	grid-area: operations;
	display: grid;
	justify-items: center;
	align-content: space-around;
}

.calc-other-grid {
	grid-area: other;
	display: grid;
	grid-auto-flow: column;
	justify-items: center;
}

.calc-btn {
	display: flex;
	align-items: center;
	justify-content: center;
	font-size: 1.5rem;
	width: 80px;
	height: 80px;
	background-color: var(--gray);
	border: 0;
	color: var(--pale-blue);
	border: 1px solid var(--dark-gray);
}

.calc-btn.is-wide {
	width: 100%;
	grid-column: 1 / span 2;
}

.calc-num-grid {
	grid-area: numbers;
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	justify-items: center;
	align-content: space-around;
}

.calc-panel {
	flex: 1;
}

.calc-total {
	margin: 0;
	padding: 1.5rem 1rem;
	font-size: 5rem;
	text-align: right;
	color: var(--pale-blue);
	max-width: 7ch;
	overflow: hidden;
	line-height: 1;
}
</style>
