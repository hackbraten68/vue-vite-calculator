<script setup>
import {ref} from 'vue';

defineProps({
  msg: String,
});

const calculatorValue = ref('');
const calculatorElements = ['C','*','/','-', 7,8,9,'+',4,5,6,'%',1,2,3,'=',0,'.'];

export default function () {
  function action(n) {
    if(!isNan(n) || n === '.') {
      this.calculatorValue += n + '';
    }
  }
}
</script>

<template>
  <div class="p-3 main" style="max-width: 400px; margin: 50px auto; background: #234;">

    <!-- Calculator Result -->
    <div class="w-full result rounded m-1 p-2 text-right lead font-weight-bold text-white bg-vue-dark">
    {{ calculatorValue || 0 }}
    </div>

    <!-- Calculator Buttons -->
    <div class="row no-gutters">
      <div class="col-3" v-for="n in calculatorElements" :key="n">
        <div class="lead text-white text-center m-1 py-3 bg-vue-dark rounded hover-class"
        :class="{'bg-vue-green': ['C','*','/','-','+','%','='].includes(n)}"
        @click="action"
        >
          {{ n }}
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.bg-vue-dark {
  background: #31475e;
}
.bg-vue-green {
  background: #3fb984;
}
.hover-class:hover {
  cursor: pointer;
  background: #3D5875;
}
.result {
  text-align: right;
}
</style>
