<script setup>
// usando 'ref()' pq sao variaveis simples, com um valor unico.
// Já o 'reactive()' é pra variaveis com varias propriedades, tipo um objeto.
import { ref } from "vue";

const campo1 = ref("");
const campo2 = ref("");
const operacao = ref("+");
const resultado = ref("");

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
    <header class="px-5 mt-5 text-center">
      <h1>VueCalc 🧮</h1>
      <p>Uma calculadora aritmética em Vue</p>
    </header>
    <section class="p-5 my-5 bg-light rounded-3">
      <div class="row">
        <div class="col text-center">
          <label>Campo 1</label>
          <input
            type="number"
            class="form-control text-center"
            placeholder="Insira um valor"
            v-model="campo1"
            @input="calcular"
          />
          <!-- v-model: conecta dados do formulário -->
          <!-- @input: atualiza os dados ao digitar -->
        </div>
        <div class="col-md-2 text-center">
          <label>Operador</label>
          <select class="form-select" v-model="operacao" @change="calcular">
            <!-- @change: atualiza os dados APÓS seleção de campo -->
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
          </select>
        </div>
        <div class="col text-center">
          <label>Campo 2</label>
          <input
            type="number"
            class="form-control text-center"
            placeholder="Insira um valor"
            v-model="campo2"
            @input="calcular"
          />
        </div>
      </div>
    </section>
    <section class="px-5 mb-5">
      <div class="row mt-3">
        <div class="col text-center">
          <p class="fs-4">Resultado: {{ resultado }}</p>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped></style>
