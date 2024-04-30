<script setup>
import { ref } from 'vue';

const emit = defineEmits(["salvar-pessoa"]);

const nome = ref('')
const cpf = ref('')
const categoria = ref('')

const evento = () => {
    emit('salvar-pessoa', nome.value, cpf.value, categoria.value);
}

</script>

<template>
    <form @submit.prevent="evento">
        <div>
            <label for="nome">Nome</label>
            <input v-model="nome" id="nome" type="text">
        </div>

        <div>
            <label for="cpf">CPF</label>
            <input v-model="cpf" id="cpf" type="text">
        </div>

        <div>
            <label for="categoria">Categoria</label>
            <input v-model="categoria" type="text" id="categoria">
        </div>

        <div>
            <button>Salvar</button>
        </div>
    </form>
</template>