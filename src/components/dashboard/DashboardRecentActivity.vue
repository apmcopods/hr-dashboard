<script setup></script>

<template>
    <div class="container rounded-borders-10">
        <div class="header pl-20 pr-10 py-10 font-poppins">Recent Activity</div>
        <div class="body">
            <div class="time">10.40 AM, Fri 10 Sept 2021</div>
            <div class="title my-6">You posted a new job</div>
            <div class="content">Kindly check the requirements and terms of work and make sure everything is right.</div>
        </div>
        <div class="footer row justify-between align-center">
            <div>Today you make 12 Activities</div>
            <button class="rounded-borders-4">See All Activity</button>
        </div>
    </div>
</template>

<style scoped>
.container {
    background: linear-gradient(0deg, rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.2)), #161E54;
    color: white;
    max-width: 424px;
}

.header {
    background: #1B204A;
    border-radius: 10px 10px 0px 0px;
}

.header,
.title,
.footer {
    font-weight: 500;
    font-size: 18px;
    line-height: 28px;
}

.body {
    padding: 26px 24px 28px;
}

.time,
.content {
    font-family: 'Roboto';
    font-weight: 500;
    font-size: 10px;
    line-height: 12px;
}

.time {
    opacity: 0.6;
}

.content {
    opacity: 0.8;
}

.footer {
    padding: 0px 24px 26px;
}

button {
    background: #FF5151;
}
</style>