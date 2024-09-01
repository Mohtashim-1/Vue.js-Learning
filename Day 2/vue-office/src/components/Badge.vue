<template>

<div :class="`${colorToClasses[color]} flex w-fit px-2 py-1 rounded-2xl text-xs font-semibold`">
{{ props.status }}
</div>

</template>

<script setup>
import { computed } from 'vue';

const statusToColor = {
    'Active'   : 'green',
    'Inactive' : 'red',
    'Paid'     : 'green',
    'Unpaid'   : 'Orange',
    'Pending'  : 'yellow',
}
const colorToClasses = {
    'green'   : 'text-green-700 bg-green-300',
    'red' : 'text-red-700 bg-red-300',
    'orange'     : 'text-amber-700 bg-amber-300',
    'yellow'   : 'text-yellow-700 bg-yellow-300',
}
const props = defineProps({
    status : String
})
// const color = statusToColor[props.status]
const color = computed(() => {
    return statusToColor[props.status]
})

</script>