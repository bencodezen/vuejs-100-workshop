<template>
  <article class="calc">
    <section class="calc-panel">
      <p class="calc-total">
		  <!-- Render expression data here -->
	  </p>
			<div class="calc-grid-btns">
				<div class="calc-grid-num">
					<!-- Generate number buttons (i.e., 1, 2, 3 ... 0, .) -->
					<!-- Element: button -->
					<!-- Class: calc-btn -->
				</div>
				<div class="calc-grid-actions">
					<!-- Generate action buttons (i.e., C, +/-, ^) -->
					<!-- Element: button -->
					<!-- Class: calc-btn -->
				</div>
				<div class="calc-grid-operations">
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
	--gray: #4a4a4a;
	--dark-gray: #3a3a3a;
	--red: #ad5153;
	--purple: #554a58;
	--teal: #538881;
}

.calc {
	display: flex;
	max-width: 320px;
	background-color: var(--dark-gray);
	box-sizing: border-box;
	overflow: hidden;
}

.calc-grid-actions {
	grid-area: actions;
	display: grid;
	grid-auto-flow: column;
	justify-items: center;
}

.calc-grid-btns {
	display: grid;
	grid-template-columns: 3fr 1fr;
	grid-template-areas:
		'actions operations'
		'numbers operations';
}

.calc-grid-num {
	grid-area: numbers;
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	justify-items: center;
	align-content: space-around;
}

.calc-grid-operations {
	grid-area: operations;
	display: grid;
	justify-items: center;
	align-content: space-around;
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
