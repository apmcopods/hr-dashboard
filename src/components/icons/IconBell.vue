<script setup>
import IconBadge from "./IconBadge.vue"

defineProps({
    showBadge: {
        type: Boolean,
        default: false
    }
});

</script>

<template>
    <span class="container">
        <svg width="19" height="20" viewBox="0 0 19 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
                d="M9.50146 20C10.8066 20 11.8745 19.0769 11.8745 17.9487H7.12843C7.12843 18.4928 7.37845 19.0145 7.82348 19.3992C8.26851 19.7839 8.8721 20 9.50146 20ZM16.6205 13.8462V8.71795C16.6205 5.56923 14.6747 2.93333 11.2812 2.2359V1.53846C11.2812 0.68718 10.4863 0 9.50146 0C8.51666 0 7.72169 0.68718 7.72169 1.53846V2.2359C4.3164 2.93333 2.38238 5.55897 2.38238 8.71795V13.8462L0.851774 15.1692C0.104271 15.8154 0.626337 16.9231 1.68233 16.9231H17.3087C18.3647 16.9231 18.8987 15.8154 18.1512 15.1692L16.6205 13.8462Z"
                fill="#B2B2B2" />
        </svg>
        <IconBadge v-if="showBadge" class="badge" />
    </span>
</template>

<style scoped>
.container {
    position: relative;
}

.badge {
    position: absolute;
    right: 0;
    top: 0;
}
</style>
