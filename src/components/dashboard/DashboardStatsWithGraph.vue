<script setup>
import { computed } from '@vue/reactivity';
import LineGraph from '../common/LineGraph.vue';

defineProps({
    title: String,
    count: Number,
    menCount: Number,
    womenCount: Number,
    percentageValue: Number
});

</script>

<template>
    <div class="row align-center gap-10 pa-20 border-grey rounded-borders-10">
        <div class="left-column col">
            <div class="title">{{ title }}</div>
            <div class="count font-rubik mt-8 mb-16">{{ count }}</div>
            <div class="count-gender mb-4">{{ menCount }} Men</div>
            <div class="count-gender">{{ womenCount }} Women</div>
        </div>
        <div class="right-column">
            <LineGraph :value="percentageValue" class="mb-20" />
            <button>+{{ percentageValue }}% Past month</button>
        </div>
    </div>
</template>

<style scoped>
.title {
    font-family: 'Poppins';
    font-weight: 500;
    font-size: 18px;
    line-height: 28px;
}

.count {
    font-size: 48px;
    line-height: 57px;
}

.count-gender {
    font-family: 'Roboto';
    font-size: 12px;
    line-height: 18px;
    color: #686868;
}

button {
    background: #FFC3A6;
    border-radius: 4px;
    padding: 0 10px;
    font-size: 12px;
    line-height: 24px;
    color: #686868;
}
</style>