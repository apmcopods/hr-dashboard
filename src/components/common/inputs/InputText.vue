<script setup>
import { ref } from 'vue';

const emit = defineEmits(['update:modelValue'])
const props = defineProps({
    label: String,
    modelValue: String,
    placeholder: String,
    type: {
        type: String,
        default: 'text'
    },
    required: {
        type: Boolean,
        default: false
    }
})
const isValid = ref(true);

function updateValue(e) {
    emit('update:modelValue', e.target.value)
    validate(e.target.value)
}

function validate(value) {
    if (props.required && !value) {
        isValid.value = false;
        return false;
    }
    isValid.value = true;
    return true;
}
</script>

<template>
    <div class="column">
        <label v-if="label" class="column">
            <span class="label-text text-black-800 pb-16">{{ label }}</span>
            <input :type="type" :value="modelValue" :placeholder="placeholder" :required="required"
                class="rounded-borders-4" :class="{ 'error': !isValid }" @input="updateValue" />
        </label>
        <span v-if="!isValid" class="error-text">Please enter the {{ label }}</span>
    </div>
</template>

<style scoped>
.label-text {
    padding-left: 16px;
    font-size: 11px;
    line-height: 12px;
}

input {
    outline: none;
    background: #FAFAFA;
    border: 1px solid #E0E0E0;
    padding: 10px 16px;
    font-size: 16px;
    line-height: 24px;
}

input.error {
    border-color: #DF0000;
}

.error-text {
    font-size: 8px;
    line-height: 12px;
    color: #DF0000;
}
</style>