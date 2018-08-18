<template>
  <div class="calculator">
    <div class="display">0.54534563461</div>
    <div class="btn">C</div>
    <div class="btn">+/-</div>
    <div class="btn">%</div>
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
export default {};
</script>

<style scoped lang="scss">
.calculator {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
  width: 400px;
  margin: 0 auto;
  font-size: 40px;
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
    background-color: #FB8C00;
    color: #fff;
  }
}
</style>
