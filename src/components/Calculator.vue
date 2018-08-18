<template>
  <div class="calculator">
    <div class="display">{{current || "0"}}</div>
    <div @click="clear" class="btn">C</div>
    <div @click="sign" class="btn">+/-</div>
    <div @click="percent" class="btn">%</div>
    <div @click="divide" class="btn operators">÷</div>
    <div @click="append('7')" class="btn">7</div>
    <div @click="append('8')" class="btn">8</div>
    <div @click="append('9')" class="btn">9</div>
    <div @click="times" class="btn operators">x</div>
    <div @click="append('4')" class="btn">4</div>
    <div @click="append('5')" class="btn">5</div>
    <div @click="append('6')" class="btn">6</div>
    <div @click="minus" class="btn operators">-</div>
    <div @click="append('1')" class="btn">1</div>
    <div @click="append('2')" class="btn">2</div>
    <div @click="append('3')" class="btn">3</div>
    <div @click="add" class="btn operators">+</div>
    <div @click="append('0')" class="btn zero">0</div>
    <div @click="dot()" class="btn">.</div>
    <div @click="equal" class="btn operators">=</div>
  </div>
</template>

<script>
export default {
	data() {
		return {
      current: "",
      previous: null,
      operatorClicked: false,
      operator: null
		};
	},
	methods: {
       setPrevious() {
       this.previous = this.current;
       this.operatorClicked = true;
    },
		clear() {
			this.current = "";
		},
		sign() {
			this.current = this.current.charAt(0) === "-" ? this.current.slice(1) : `-${this.current}`;
		},
		percent() {
			this.current = `${parseFloat(this.current) / 100}`;
		},
		append(number) {
			this.current = `${this.current}${number}`;
    },
    dot() {
      if(this.current.indexOf('.') === -1) {
        this.append('.')
      }
    },
    divide() {
      this.operator = (num1, num2) => num1 / num2;
      this.setPrevious();
    },
    times() {
      this.operator = (num1, num2) => num1 * num2;
      this.setPrevious();
    },
    minus() {
      this.operator = (num1, num2) => num1 - num2;
      this.setPrevious();
    },
    add() {
      this.operator = (num1, num2) => num1 + num2;
      this.setPrevious();
    },
    equal(){
      
    }
 
	}
};
</script>

<style scoped lang="scss">
.calculator {
	display: grid;
	grid-template-columns: repeat(4, 1fr);
	grid-auto-rows: minmax(50px, auto);
	width: 400px;
	margin: 0 auto;
	font-size: 40px;
	cursor: pointer;
	.display {
		grid-column: 1 / 5;
		background-color: #212121;
		color: #fff;
	}
	.zero {
		grid-column: 1 / 3;
	}
	.btn {
		background-color: #f2f2f2;
		border: 1px solid #999;
	}
	.operators {
		background-color: #fb8c00;
		color: #fff;
	}
}
</style>
