<template>
  <div class="calculator">
    <div class="display">{{current || "0"}}</div>
    <div @click="clear" class="btn">C</div>
    <div @click="sign" class="btn">+/-</div>
    <div @click="percent" class="btn">%</div>
    <div class="btn operators">÷</div>
    <div class="btn">7</div>
    <div class="btn">8</div>
    <div class="btn">9</div>
    <div class="btn operators">x</div>
    <div class="btn">4</div>
    <div class="btn">5</div>
    <div class="btn">6</div>
    <div class="btn operators">-</div>
    <div class="btn">1</div>
    <div class="btn">2</div>
    <div class="btn">3</div>
    <div class="btn operators">+</div>
    <div class="btn zero">0</div>
    <div class="btn">.</div>
    <div class="btn operators">=</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      current: "600"
    }
  },
  methods: {
    clear() {
      this.current = "";
    },
    sign() {
      this.current = this.current.charAt(0) === '-' ?
        this.current.slice(1) : `-${this.current}`;
    },
    percent() {
      this.current = `${parseFloat(this.current) / 100}`
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
    text-align: right;
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
    background-color: #FB8C00;
    color: #fff;
  }
}
</style>
