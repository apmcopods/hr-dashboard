<script setup>
import IconPin from '../icons/IconPin.vue';
import IconMenuDots from '../icons/IconMenuDots.vue';

</script>

<template>
    <div class="container row justify-between border-grey border-.5 rounded-borders-6 py-12 px-16">
        <div>
            <div class="message font-poppins mb-6">Outing schedule for every department</div>
            <div class="time">5 minutes ago</div>
        </div>
        <div class="actions row align-center gap-24">
            <IconPin />
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