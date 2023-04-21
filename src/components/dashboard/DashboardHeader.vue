<script setup>
import IconBell from '../icons/IconBell.vue';
import IconBurger from '../icons/IconBurger.vue';
import IconChevronDown from '../icons/IconChevronDown.vue';
import IconMessage from '../icons/IconMessage.vue';
import IconSearch from '../icons/IconSearch.vue';

</script>

<template>
    <div class="header row align-center justify-between">
        <div class="row align-center gap-16">
            <IconBurger class="mobile-and-tablet-only" />
            <div class="input-container row justify-between align-center px-16 py-10 rounded-borders-4">
                <input placeholder="Search" class="mr-8" />
                <IconSearch />
            </div>
            <IconSearch class="mobile-only" />
        </div>
        <div class="row align-center gap-36">
            <IconBell :show-badge="true" />
            <IconMessage />
            <div class="row align-center gap-10">
                <img src="/avatar.png" class="avatar" />
                <div class="username">Admirra John</div>
                <IconChevronDown />
            </div>
        </div>
    </div>
</template>

<style scoped>
.header {
    padding: 24px 50px 24px 0px;
    margin-left: 50px;
    border-bottom: 1px solid #F1F1F1;
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

.mobile-only,
.mobile-and-tablet-only {
    display: none;
}

@media screen and (max-width: 1028px) {
    .username {
        display: none;
    }

    .input-container {
        min-width: 245px;
    }
}

@media screen and (max-width: 940px) {
    .input-container {
        min-width: 120px;
    }

    .header {
        padding-left: 12px;
        padding-right: 24px;
        margin-left: 0px;
    }


    .mobile-and-tablet-only {
        display: block;
    }
}

@media screen and (max-width: 640px) {
    .input-container {
        display: none;
    }

    .header {
        padding-right: 12px;
    }

    .mobile-only {
        display: block;
    }
}
</style>