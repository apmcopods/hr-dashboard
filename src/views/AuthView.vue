<script setup>
import { ref } from 'vue';
import InputText from '@/components/common/inputs/InputText.vue';
import { computed } from '@vue/reactivity';

const isLoginMode = ref(true);
const name = ref("")
const email = ref("");
const password = ref("");

const tagline = computed(() => isLoginMode.value ? 'Nice to see you again' : 'Register');
const normalBtnText = computed(() => isLoginMode.value ? 'Sign in' : 'Sign up');
const googleBtnText = computed(() => `Or sign ${isLoginMode.value ? 'in' : 'up'} with Google`);
const redirectionText = computed(() => isLoginMode.value ? 'Don\'t have an account?' : 'Already have an account?');
const redirectionLinkText = computed(() => isLoginMode.value ? 'Sign up now' : 'Sign in now');


</script>

<template>
    <div class="row">
        <img src="/boat.png" class="left-section" />
        <div class="right-section column justify-between overflow-y-scroll">
            <form class="column ma-48">
                <div class="logo mx-auto">WeHR</div>
                <h3 class="mt-60 mb-24 tagline font-poppins">{{ tagline }}</h3>
                <InputText v-model="name" v-if="!isLoginMode" label="Name" placeholder="Enter name" :required="true"
                    class="mb-16" />
                <InputText v-model="email" label="Email" placeholder="Enter email" :required="true" type="email" />
                <InputText v-model="password" label="Password" placeholder="Enter password" :required="true" type="password"
                    class="mt-16 mb-20" />
                <a v-if="isLoginMode" class="align-self-end mb-20">Forgot password?</a>
                <button class="btn-signin mt-12">{{ normalBtnText }}</button>
                <hr class="my-32" />
                <button class="btn-google">
                    <img src="https://www.jigsawplanet.com/John1333/Google-G-Logo-svg?rc=face" height="20" width="20" />
                    {{ googleBtnText }}
                </button>
                <div class="row gap-8 mx-auto mt-24 signup-section">
                    <span>{{ redirectionText }}</span>
                    <a @click="() => isLoginMode = !isLoginMode">{{ redirectionLinkText }}</a>
                </div>
            </form>
            <div class="copyright-text mx-auto mb-32">© Perfect Login 2023</div>
        </div>
    </div>
</template>

<style scoped>
.left-section {
    width: 65%;
    height: 100vh;
}

.right-section {
    width: 35%;
    max-height: 100vh;
}

.logo {
    margin-top: 10px;
}

.tagline {
    font-weight: 600;
    font-size: 20px;
    line-height: 28px;
    color: #1A1A1A;
}

.btn-signin {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    font-size: 15px;
    line-height: 20px;
    background: #007AFF;
}

.btn-google {
    background-color: black;
}

.signup-section {
    font-size: 12px;
    line-height: 20px;
}

.copyright-text {
    font-size: 12px;
    line-height: 16px;
    color: #666;
}
</style>