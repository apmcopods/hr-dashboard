<script setup>
defineProps({
    type: {
        type: String,
        default: 'needed'
    },
    title: String,
    count: Number,
    subtitle: String
});
</script>

<template>
    <div :data-type="type" class="container py-12 pl-20 pr-12 rounded-borders-10">
        <div class="title font-poppins">{{ title }}</div>
        <div class="count my-16">{{ count }}</div>
        <div class="bottom-text">{{ subtitle }}</div>
    </div>
</template>

<style scoped>
.container {
    max-width: 204px;
}

.container[data-type='needed'] {
    background: #FFEFE7;
}

.container[data-type='hiring'] {
    background: #E8F0FB;
}

.container[data-type='hired'] {
    background: #FDEBF9;
}

.title {
    font-weight: 500;
    font-size: 18px;
    line-height: 28px;
}

.count {
    font-weight: 500;
    font-size: 36px;
    line-height: 28px;
}

.bottom-text {
    font-family: 'Roboto';
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
}

.container[data-type='needed'] .bottom-text {
    color: #FF5151;
}

.container[data-type='hiring'] .bottom-text {
    color: #3786F1;
}

.container[data-type='hired'] .bottom-text {
    color: #EE61CF;
}
</style>