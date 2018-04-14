<template>
  <article class="calc">
    <section class="calc-panel">
      <p class="calc-total">{{ expression }}</p>
			<div class="calc-btn-grid">
				<div class="calc-num-grid">
					<button v-for="item in buttons"
						@click="updateEquation"
						class="calc-btn"
						:class="item === 0 ? 'is-wide' : ''"
						:key="item"
						:value="item"
					>
						{{ item }}
					</button>
				</div>
				<div class="calc-other-grid">
					<button v-for="action in actions"
						@click="updateEquation"
						class="calc-btn"
						style="background-color: #47B784"
						:style="action === 'C' ? 'background-color: var(--red)' : ''"
						:key="action"
						:value="action"
					>
						{{ action }}
					</button>
				</div>
				<div class="calc-operations-grid">
					<button v-for="operation in operations"
						@click="updateEquation"
						class="calc-btn"
						style="background-color: #9770E9"
						:key="operation"
						:value="operation"
					>
						{{ operation }}
					</button>
				</div>
			</div>
    </section>
  </article>
</template>

<script>
export default {
	name: 'Calculator',
	data() {
		return {
			actions: ['C', '+/-', '^'],
			buttons: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0, '.'],
			operations: ['/', '*', '-', '+', '='],
			expression: '0',
			total: 0
		}
	},
	methods: {
		updateEquation(event) {
			const buttonValue = event.target.value

			if (buttonValue === 'C') {
				this.expression = '0'
			} else if (buttonValue === '=') {
				this.expression = eval(this.expression)
			} else if (buttonValue === '^') {
				this.expression += '**'
			} else if (buttonValue === '+/-') {
				if (this.expression[0] === '-') {
					this.expression = this.expression.substring(1)
				} else {
					this.expression = '-' + this.expression
				}
			} else if (this.expression === '0') {
				this.expression = buttonValue
			} else if (this.expression === '-0') {
				this.expression = '-' + buttonValue
			} else {
				this.expression += buttonValue
			}
		}
	}
}
</script>

<style>
:root {
	--gray: #606060;
	--pale-blue: #ebf6fc;
	--midnight-blue: #1b2b32;
	--red: #ad5153;
	--teal: #3a646e;

	--row-gutter: 20px;
}

.calc {
	display: grid;
}

.calc {
	display: flex;
	max-width: 360px;
	padding: 20px;
	margin: 0 auto;
	background-color: var(--midnight-blue);
	box-sizing: border-box;
	overflow: hidden;
}

.calc-btn-grid {
	display: grid;
	grid-template-columns: 3fr 1fr;
	grid-template-areas:
		'other operations'
		'numbers operations';
	grid-row-gap: var(--row-gutter);
}

.calc-operations-grid {
	grid-area: operations;
	display: grid;
	justify-items: center;
	align-content: space-around;
	grid-row-gap: var(--row-gutter);
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
	border-radius: 50%;
	font-size: 1.5rem;
	width: 60px;
	height: 60px;
	background-color: var(--gray);
	border: 0;
	color: var(--pale-blue);
}

.calc-btn.is-wide {
	width: 100%;
	grid-column: 1 / span 2;
	border-radius: 30px;
}

.calc-num-grid {
	grid-area: numbers;
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	grid-row-gap: var(--row-gutter);
	justify-items: center;
	align-content: space-around;
}

.calc-panel {
	flex: 1;
}

.calc-total {
	margin: 0;
	padding-bottom: 1rem;
	font-size: 5rem;
	text-align: right;
	color: var(--pale-blue);
	max-width: 7ch;
	overflow: hidden;
}
</style>
