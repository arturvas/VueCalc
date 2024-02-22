<script setup>
// usando 'ref()' pq sao variaveis simples, com um valor unico.
// Já o 'reactive()' é pra variaveis com varias propriedades, tipo um objeto.
import { ref } from "vue";
import Title from "./components/Title.vue";
import Operator from "./components/Operator.vue";
import Result from "./components/Result.vue";

const campo1 = ref();
const campo2 = ref();
const operacao = ref("+");
const resultado = ref();

const calcular = () => {
  switch (operacao.value) {
    case "+":
      resultado.value = campo1.value + campo2.value;
      break;
    case "-":
      resultado.value = campo1.value - campo2.value;
      break;
    case "*":
      resultado.value = campo1.value * campo2.value;
      break;
    case "/":
      resultado.value = campo1.value / campo2.value;
      break;
    default:
      resultado.value = 0;
  }
};
</script>

<template>
  <div class="container">
    <Title></Title>
    <Operator
      v-model:x="campo1"
      v-model:op="operacao"
      v-model:y="campo2"
      :calcular="calcular"
    ></Operator>
    <Result :resultado="resultado"></Result>
  </div>
</template>

<style scoped></style>
