<script setup>
import { ref } from 'vue';

defineProps({
  msg: String,
});

const count = ref(0);
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="container">
    <div class="result">TEST</div>
    <div class="zero digits">0</div>
    <div class="one digits">1</div>
    <div class="two digits">2</div>
    <div class="three digits">3</div>
    <div class="four digits">4</div>
    <div class="five digits">5</div>
    <div class="six digits">6</div>
    <div class="seven digits">7</div>
    <div class="eight digits">8</div>
    <div class="nine digits">9</div>
    <div class="enter">ENTER</div>
    <div class="plus operators">+</div>
    <div class="minus operators">-</div>
    <div class="multi operators">*</div>
    <div class="divi operators">/</div>
  </div>
</template>

<style scoped>
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr 1fr;
  gap: 0px 0px;
  grid-auto-flow: row;
  grid-template-areas:
    'result result result result result'
    'seven eight nine multi divi'
    'four five six plus minus'
    'one two three zero enter';

  border: 1px solid red;
  width: 85vw;
  height: 250px;
}

.digits {
  border: 1px solid green;
}

.operators {
  border: 1px solid red;
}

.result {
  grid-area: result;
  border: 1px solid white;
}

.zero {
  grid-area: zero;
}

.one {
  grid-area: one;
  border: 1px solid green;
}

.two {
  grid-area: two;
  border: 1px solid green;
}

.three {
  grid-area: three;
  border: 1px solid green;
}

.four {
  grid-area: four;
  border: 1px solid green;
}

.five {
  grid-area: five;
  border: 1px solid green;
}

.six {
  grid-area: six;
}

.seven {
  grid-area: seven;
}

.eight {
  grid-area: eight;
}

.nine {
  grid-area: nine;
}

.enter {
  grid-area: enter;
  border: 1px solid blue;
}

.plus {
  grid-area: plus;
}

.minus {
  grid-area: minus;
}

.multi {
  grid-area: multi;
}

.divi {
  grid-area: divi;
}
</style>
