<script setup>
const props = defineProps({
  campo1: Number,
  campo2: Number,
  calcular: Function, // função recebida por prop
  operacao: String,
});
</script>

<template>
  <section class="p-5 my-5 bg-light rounded-3">
    <div class="row">
      <div class="col text-center">
        <label>Campo 1</label>
        <input
          type="number"
          class="form-control text-center"
          placeholder="Insira um valor"
          v-model="props.campo1"
          @input="props.calcular"
        />
        <!-- v-model: conecta dados do formulário -->
        <!-- @input: atualiza os dados ao digitar -->
      </div>
      <div class="col-md-2 text-center">
        <label>Operador</label>
        <select
          class="form-select"
          v-model="props.operacao"
          @change="props.calcular"
        >
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
          v-model="props.campo2"
          @input="props.calcular"
        />
      </div>
    </div>
  </section>
</template>
