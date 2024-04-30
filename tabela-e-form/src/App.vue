<script setup>
import Form from "./components/Form.vue";
import Tabela from "./components/Tabela.vue";

import {ref, onMounted} from 'vue';

const lista = ref([]);

onMounted(() => {
  fetch("https://pokeapi.co/api/v2/pokemon")
})

const evento = (nome, cpf, categoria) => {
  const item = {
    nome, 
    cpf, 
    categoria
  };
  console.log(item)
  lista.value.push(item)
}

</script>

<template>
  <main>
    <Form @salvar-pessoa="evento" />
    <Tabela :lista="lista" />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
