<script setup>
import IconBell from '../icons/IconBell.vue';
import IconChevronDown from '../icons/IconChevronDown.vue';
import IconMessage from '../icons/IconMessage.vue';
import IconSearch from '../icons/IconSearch.vue';

</script>

<template>
    <div class="header row align-center justify-between">
        <div class="input-container row justify-between align-center px-16 py-10 rounded-borders-4">
            <input placeholder="Search" class="mr-8" />
            <IconSearch />
        </div>
        <div class="row align-center gap-36">
            <IconBell :show-badge="true" />
            <IconMessage />
            <div class="row align-center gap-10">
                <img src="/avatar.png" class="avatar" />
                <div>Admirra John</div>
                <IconChevronDown />
            </div>
        </div>
    </div>
</template>

<style scoped>
.header {
    padding: 24px 50px;
}

.input-container {
    background: #fafafa;
    min-width: 343px;
}

input {
    outline: none;
    border: none;
    padding: 0;
    background: rgba(255, 255, 255, 0);
}

.avatar {
    border-radius: 100%;
}
</style>