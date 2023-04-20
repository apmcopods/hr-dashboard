<script setup>
import DashboardScheduleListItem from './DashboardScheduleListItem.vue';

defineProps({
    values: {
        type: Array,
        default: []
    },
    title: String,
    bottomText: String,
    showPin: {
        type: Boolean,
        default: true
    }
});

</script>

<template>
    <div class="border-grey rounded-borders-12">
        <div class="header font-poppins row justify-between pt-16 px-20 mb-16">
            {{ title }}
            <input type="date" class="border-lightgrey rounded-borders-4" />
        </div>
        <div class="list overflow-y-scroll px-20">
            <div v-for="item in values" :key="item.id" class="column gap-8 mb-8">
                <div v-if="item.label" class="label">{{ item.label }}</div>
                <DashboardScheduleListItem v-for="listItem in item.data" :key="listItem.id" :message="listItem.message"
                    :time="listItem.time" :show-pin="showPin" />
            </div>
        </div>
        <div class="bottom-text pa-10 cursor-pointer font-poppins">
            {{ bottomText }}
        </div>
    </div>
</template>

<style scoped>
.header,
input,
.bottom-text {
    font-weight: 500;
    font-size: 18px;
    line-height: 28px;
}

input {
    outline: none;
    color: #686868;
    font-family: 'Roboto';
    padding: 2px 8px;
    height: 27px;
}

.label {
    font-size: 12px;
    line-height: 28px;
    color: #686868;
}

.list {
    border-bottom: 1px solid #E0E0E0;
    max-height: 320px;
}

.bottom-text {
    color: #FF5151;
    text-align: center;
}
</style>