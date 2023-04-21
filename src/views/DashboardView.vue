<script setup>
import DashboardStatsColored from '@/components/dashboard/DashboardStatsColored.vue';
import DashboardStatsWithGraph from '@/components/dashboard/DashboardStatsWithGraph.vue';
import DashboardRecentActivity from '@/components/dashboard/DashboardRecentActivity.vue';
import DashboardScheduleList from '@/components/dashboard/DashboardScheduleList.vue';
import DashboardHeader from '../components/dashboard/DashboardHeader.vue';
import DashboardSidebar from '../components/dashboard/DashboardSidebar.vue';

const coloredStats = [
    {
        id: 'stat-1',
        type: 'needed',
        title: 'Available Position',
        count: 24,
        subtitle: '4 Urgently needed'
    },
    {
        id: 'stat-2',
        type: 'hiring',
        title: 'Job Open',
        count: 10,
        subtitle: '4 Active hiring'
    },
    {
        id: 'stat-3',
        type: 'hired',
        title: 'New Employees',
        count: 24,
        subtitle: '4 Department'
    },
];

const graphStats = [
    {
        id: 'stat-4',
        title: 'Total Employees',
        count: 216,
        menCount: 120,
        womenCount: 96,
        percentageValue: 2
    },
    {
        id: 'stat-5',
        title: 'Talent Request',
        count: 16,
        menCount: 6,
        womenCount: 10,
        percentageValue: 5
    }
]



const announcements = [
    {
        id: 1,
        label: '',
        data: [
            {
                id: 2,
                message: 'Outing schedule for every departement',
                time: '5 minutes ago'
            },
            {
                id: 3,
                message: 'Meeting HR Department',
                time: 'Yesterday, 12:30 PM'
            },
            {
                id: 4,
                message: 'IT Department need two more talents for UX/UI Designer position',
                time: 'Yesterday, 09:15 AM'
            },
        ]
    }
];

const scheduleList = [
    {
        id: 5,
        label: 'Priority',
        data: [
            {
                id: 6,
                message: 'Review candidate applications',
                time: 'Today - 11.30 AM'
            }
        ]
    },
    {
        id: 7,
        label: 'Other',
        data: [
            {
                id: 8,
                message: 'Interview with candidates',
                time: 'Today - 10.30 AM'
            },
            {
                id: 9,
                message: 'Short meeting with product designer from IT Departement',
                time: 'Today - 10.30 AM'
            },
            {
                id: 10,
                message: 'Submit review report for previous interviews',
                time: 'Today, 09:15 AM'
            },
        ]
    }
];
</script>

<template>
    <main class="row">

        <DashboardSidebar class="sidebar" />
        <div class="dashboard-body">
            <DashboardHeader class="dashboard-header" />
            <div class="dashboard-content row overflow-y-scroll">
                <div class="dashboard-content-left column">
                    <div class="tab-title font-poppins mt-10 py-10">Dashboard</div>
                    <div class="dashboard-stats-colored-container row justify-between">
                        <DashboardStatsColored v-for="stat in coloredStats" :key="stat.id" :type="stat.type"
                            :title="stat.title" :count="stat.count" :subtitle="stat.subtitle"
                            class="dashboard-stat-colored col" />
                    </div>
                    <div class="dashboard-stats-graph-container row justify-between my-20 wrap">
                        <DashboardStatsWithGraph v-for="stat in graphStats" :key="stat.id" :title="stat.title"
                            :count="stat.count" :men-count="stat.menCount" :women-count="stat.womenCount"
                            :percentage-value="stat.percentageValue" class="dashboard-stat-graph col" />
                    </div>
                    <DashboardScheduleList :values="announcements" title="Announcements" bottom-text="See All Announcements"
                        class="dashboard-announcement" />
                </div>
                <div class="dashboard-content-right column gap-20">
                    <DashboardRecentActivity class="recent-activity col" />
                    <DashboardScheduleList :values="scheduleList" title="Upcoming schedule"
                        bottom-text="Create a New Schedule" class="dashboard-schedule col" />
                </div>
            </div>

        </div>
    </main>
</template>

<style scoped>
.sidebar {
    width: 16.8%;
    min-width: 180px;
}

.dashboard-header {
    height: 12.5vh;
}

.dashboard-body {
    flex: 1;
}

.dashboard-content {
    height: 85vh;
    padding: 0px 50px;
    gap: 30px;
}

.dashboard-content-left {
    width: 60%;
}

.dashboard-content-right {
    margin-top: 72px;
    width: 40%;
}

.dashboard-stats-colored-container,
.dashboard-stats-graph-container {
    gap: 14px;
}

.tab-title {
    font-weight: 500;
    font-size: 24px;
    line-height: 42px;
}

@media screen and (max-width: 1024px) and (min-width: 941px) {
    .dashboard-stats-colored-container {
        flex-wrap: wrap;
    }

    .dashboard-stat-colored {
        flex-wrap: wrap;
        flex: unset;
        width: 100%;
    }

}

@media screen and (max-width: 940px) {
    .sidebar {
        width: 90px;
        min-width: 90px;
    }

    .dashboard-stats-graph-container,
    .dashboard-content {
        flex-wrap: wrap;
    }


    .dashboard-content-left {
        width: 100%;
    }

    .dashboard-content-right {
        flex-direction: row;
        width: 100%;
        max-height: 345px;
        margin-top: 0px;
    }
}

@media screen and (max-width: 820px) {
    .dashboard-content-right {
        flex-wrap: wrap;
        flex-direction: row-reverse;
    }

    .recent-activity,
    .dashboard-schedule {
        flex: unset;
        width: 100%;
    }
}

@media screen and (max-width: 640px) {
    .dashboard-stats-colored-container {
        flex-wrap: wrap;
    }

    .dashboard-stat-colored {
        flex: unset;
        width: 100%;
    }

}

@media screen and (max-width: 390px) {
    .sidebar {
        display: none;
    }

}
</style>