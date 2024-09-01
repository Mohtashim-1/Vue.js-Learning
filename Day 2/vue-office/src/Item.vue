<template>
<h1>{{ props.name }}</h1>
</template>

<script setup>
const props = defineProps({
    name: String
})
</script>