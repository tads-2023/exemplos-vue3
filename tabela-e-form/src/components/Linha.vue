<script setup>
const props = defineProps(["item"]);
</script>

<template>
    <tr>
        <td>{{ item.nome }}</td>
        <td>{{ item.cpf }}</td>
        <td>{{ item.categoria }}</td>
        <td></td>
    </tr>
</template>