<script setup>
import { useRoute } from 'vue-router';


const menu = [
    {
        id: 1,
        header: 'MAIN MENU',
        menuOptions: [
            {
                id: 2,
                label: 'Dashboard',
                icon: '/dashboard.svg',
                route: '/'
            },
            {
                id: 3,
                label: 'Recruitment',
                icon: '/recruitment.svg',
                route: '/recruitment'
            },
            {
                id: 4,
                label: 'Schedule',
                icon: '/calendar.svg',
                route: '/calendar'
            },
            {
                id: 5,
                label: 'Employee',
                icon: '/employee.svg',
                route: '/employee'
            },
            {
                id: 6,
                label: 'Department',
                icon: '/department.svg',
                route: '/department'
            },
        ]
    },
    {
        id: 7,
        header: 'OTHER',
        menuOptions: [
            {
                id: 8,
                label: 'Support',
                icon: '/support.svg',
                route: '/support'
            },
            {
                id: 9,
                label: 'Settings',
                icon: '/settings.svg',
                route: '/settings'
            },
        ]
    },
];

const route = useRoute();

</script>

<template>
    <div class="container column py-20">
        <div class="logo-black font-poppins pa-10 mb-48 mx-auto">
            WeHR
        </div>
        <div class="column align-start gap-40">
            <div v-for="section in menu" :key="section.id" class="full-width">
                <div class="menu-header my-10 pl-30"> {{ section.header }} </div>
                <div v-for="menuOption in section.menuOptions" :id="menuOption.id"
                    class="menu row align-center gap-24 py-16 pl-30 cursor-pointer"
                    :class="{ active: menuOption.route === route.fullPath }">
                    <img :src="menuOption.icon" />
                    <div class="menu-label">{{ menuOption.label }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.container {
    height: 100vh;
    background: #FAFAFA;
}

.logo-black {
    font-weight: 600;
    font-size: 36px;
    line-height: 42px;
    color: #000;
}

.menu-header {
    font-family: 'Roboto';
    font-weight: 500;
    font-size: 12px;
    line-height: 18px;
    color: #686868;
    opacity: 0.5;
}

.menu.active {
    cursor: default;
}

.menu.active .menu-label {
    color: #FF5151;
}

.menu:not(.active):hover {
    background: #FF5151;
    color: white;
}

.menu:not(.active):hover {
    background: #FF5151;
    color: white;
}

@media screen and (max-width: 940px) and (min-width: 391px) {
    .container {
        padding-top: 41px;
    }

    .logo-black {
        font-weight: 600;
        font-size: 20px;
        line-height: 42px;
        padding: 0;
        margin-bottom: 40px;
    }

    .menu {
        padding: 20px 0px;
        justify-content: center;
    }

    .menu-label {
        display: none;
    }

    .menu-header {
        padding: 0px;
        margin: 0;
        text-align: center;
    }
}

@media screen and (max-width: 390px) {}
</style>