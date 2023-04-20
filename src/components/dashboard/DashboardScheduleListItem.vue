<script setup>
import IconPin from '../icons/IconPin.vue';
import IconMenuDots from '../icons/IconMenuDots.vue';

defineProps({
    message: String,
    time: String,
    showPin: {
        type: Boolean,
        default: true
    }
})

</script>

<template>
    <div class="container row justify-between border-grey border-.5 rounded-borders-6 py-12 px-16">
        <div>
            <div class="message font-poppins mb-6">{{ message }}</div>
            <div class="time">{{ time }}</div>
        </div>
        <div class="actions row align-center gap-24">
            <IconPin v-if="showPin" />
            <IconMenuDots />
        </div>
    </div>
</template>

<style scoped>
.container {
    background: #fafafa;
}

.message {
    font-size: 16px;
    line-height: 24px;
}

.time {
    font-family: 'Roboto';
    font-weight: 400;
    font-size: 10px;
    line-height: 14px;
}
</style>