<script setup>
import Linha from './Linha.vue';

const props = defineProps(["lista"]);
</script>

<template>
    <table>
        <thead>
            <th>Nome</th>
            <th>CPF</th>
            <th>Categoria</th>
            <th>Ações</th>
        </thead>

        <tbody>
            <Linha 
                v-for="item in lista" 
                :item="item"
            />
        </tbody>
    </table>

</template>