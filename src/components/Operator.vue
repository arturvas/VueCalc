<script setup>
const props = defineProps({ calcular: Function });
const x = defineModel("x");
const y = defineModel("y");
const op = defineModel("op");
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
          v-model="x"
          @input="props.calcular"
        />
        <!-- v-model: conecta dados do formulário -->
        <!-- @input: atualiza os dados ao digitar -->
      </div>
      <div class="col-md-2 text-center">
        <label>Operador</label>
        <select class="form-select" v-model="op" @change="props.calcular">
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
          v-model="y"
          @input="props.calcular"
        />
      </div>
    </div>
  </section>
</template>
