<script setup>
defineProps({
    value: {
        type: Number,
        default: 2
    }
});
</script>
<template>
    <div class="container">
        <img v-if="value === 2" src="/line-graph-2.svg" alt="Line graph with value 2%" />
        <img v-else-if="value === 5" src="/line-graph-5.svg" alt="Line graph with value 5%" />
    </div>
</template>