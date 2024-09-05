<!-- Header -->
<template>
  <q-layout view="hHh lpR fFf">
    <q-header reveal elevated class="bg-negative text-white">
      <q-toolbar>
        <q-btn flat round dense icon="menu" @click="toggleDrawer" class="q-mr-sm" />
        <div class="col">
          <div class="row q-pa-xs" style="align-items: center">
            <q-avatar square class="q-ma-sm">
              <img src="../assets/Satnusa-White.png" />
            </q-avatar>
            <q-toolbar-title>
              <div class="logo-title">MySatnusa Platform</div>
              <div class="logo-subtitle">
                Project Management Tools
              </div>
            </q-toolbar-title>

            <!-- user profile -->
            <div style="text-align: end">
              <div class="row items-center q-gutter-sm">
                <div class="column">
                  <div class="text-h6 text-weight-light">
                    <span class="logo-title">Febby</span>
                  </div>
                  <div class="logo-subtitle">
                    Product Designer
                  </div>
                </div>
                <q-avatar size="32px">
                  <img src="https://dummyjson.com/icon/emilys/128" />
                </q-avatar>
                <!-- <q-icon name="stat_minus_1" /> -->
              </div>
            </div>
          </div>
        </div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <q-page padding class="q-pa-md">
        <!-- Project Summary -->
        <div class="row">
          <div class="col-8 q-gutter-md"
            style="padding: none; border-right: 2px solid rgba(0, 0, 0, 0.1); box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);">
            <div class="q-gutter-md">
              <div class="header-container">
                <div class="logo-page">Project Summary</div>
                <div class="button-group">
                  <q-btn flat icon="edit_document" label="Note (10)" :style="{
                    'text-transform': 'none',
                    'font-size': '13px',
                    'border-radius': '11px',
                    padding: '3px 3px',
                    border: '1px solid #CED3D7',
                    color: '#585858',
                  }" />
                  <q-btn flat icon="checklist" label="Task (20)" :style="{
                    'text-transform': 'none',
                    'font-size': '13px',
                    'border-radius': '11px',
                    padding: '3px 3px',
                    border: '1px solid #CED3D7',
                    color: '#585858',
                  }" />
                </div>
              </div>
              <div class="title-page">
                Good Morning, Febby Syaiful Pratama
              </div>
              <div class="card-custom">
                <div class="col-4">
                  <q-card class="q-pa-md">
                    <div class="text-agile">Project Management Agile Board 2.0 <q-btn flat dense icon="more_vert"
                        class="btnagile" @click="menu = true">
                        <q-menu>
                          <q-list dense>
                            <q-item clickable v-close-popup>
                              <q-item-section>View Project</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Share</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Planning</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Roadmaps</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Activities</q-item-section>
                            </q-item>
                          </q-list>
                        </q-menu>
                      </q-btn>
                    </div>
                    <div class="progress-and-members">
                      <div class="progress-container">
                        <q-circular-progress size="99px" font-size="15px" :value="40" color="pink" track-color="grey-3"
                          show-value>Progress <br> 40%</q-circular-progress>
                      </div>
                      <div class="members-container">
                        <div>15 Members</div>
                        <div class="avatar-container">
                          <div class="avatar-group">
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="more-count">+10</div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </q-card>
                </div>
                <div class="col-4">
                  <q-card class="q-pa-md ">
                    <div class="text-cora">CORA 2.0 <q-btn flat dense icon="more_vert" class="btncora"
                        @click="menu = true">
                        <q-menu>
                          <q-list dense>
                            <q-item clickable v-close-popup>
                              <q-item-section>View Project</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Share</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Planning</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Roadmaps</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Activities</q-item-section>
                            </q-item>
                          </q-list>
                        </q-menu>
                      </q-btn>
                    </div>
                    <div class="progress-and-members">
                      <div class="progress-container">
                        <q-circular-progress size="99px" font-size="15px" :value="90" color="green" track-color="grey-3"
                          show-value>Progress <br> 90%</q-circular-progress>
                      </div>
                      <div class="members-container">
                        <div>15 Members</div>
                        <div class="avatar-container">
                          <div class="avatar-group">
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="more-count">+10</div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </q-card>
                </div>
                <div class="col-4">
                  <q-card class="q-pa-md ">
                    <div class="text-plant">Plant Maintenance Phase 3 <q-btn flat dense icon="more_vert"
                        class="btnplant" @click="menu = true">
                        <q-menu>
                          <q-list dense style="min-width: 200px">
                            <q-item clickable v-close-popup>
                              <q-item-section>View Project</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Share</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Planning</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Roadmaps</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section>Activities</q-item-section>
                            </q-item>
                          </q-list>
                        </q-menu>
                      </q-btn>
                    </div>
                    <div class="progress-and-members">
                      <div class="progress-container">
                        <q-circular-progress size="99px" font-size="15px" :value="70" color="yellow"
                          track-color="grey-3" show-value>Progress <br> 70%</q-circular-progress>
                      </div>
                      <div class="members-container">
                        <div>15 Members</div>
                        <div class="avatar-container">
                          <div class="avatar-group">
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
                            <div class="more-count">+10</div>
                          </div>

                        </div>
                      </div>
                    </div>
                  </q-card>
                </div>
              </div>
              <!-- EPIC kiri  -->
              <div class="col">
                <div class="epic-container">
                  <div class="logo-page">Epic</div>
                  <span style="
      background-color: pink;
      color: black;
      border-radius: 15%;
      padding: 3px 6px;
      font-size: 12px;
    ">
                    20
                  </span>
                  <q-btn class="button-search" flat icon="search" label="Search" :style="{
                    'text-transform': 'none',
                    'font-size': '16px',
                    'border-radius': '12px',
                    'padding-left': '15px',
                    'align-items': 'center',
                    height: '20px',
                    border: '1px solid #CED3D7',
                    color: '#585858',
                    width: '250px',
                  }" />
                </div>
                <div class="row q-gutter-md">
                  <q-card class="q-pa-xs card-table">

                    <q-table :rows="rows" :columns="columns" flat table-style="table-layout: auto;"
                      :pagination="initialPagination" hide-bottom>
                      <template v-slot:body-cell="props">
                        <q-td :props="props">
                          <div v-if="props.col.field === 'progress'" class="q-mt-xs flex items-center">
                            <span>{{ props.row.progress }}%</span>
                            <q-icon name="more_vert" class="q-ml-xl cursor-pointer absolute"
                              @click="onIconClick(props.row)" />
                            <q-menu>
                              <q-list dense style="min-width: 200px">
                                <q-item clickable v-close-popup>
                                  <q-item-section>Detail</q-item-section>
                                </q-item>
                                <q-item clickable v-close-popup>
                                  <q-item-section>Share</q-item-section>
                                </q-item>
                              </q-list>
                            </q-menu>
                          </div>
                          <div v-else-if="props.col.field === 'stakeholders'" class="q-gutter-xs flex">
                            <div class="sketh" style="background-image: url('path/to/avatar1.jpg');"></div>
                          </div>
                          <q-badge v-else-if="props.col.field === 'type'" :color="typeColor(props.row.type)"
                            align="center">
                            {{ props.row.type }}
                          </q-badge>
                          <div v-else>
                            {{ props.row[props.col.field] }}
                          </div>
                        </q-td>
                      </template>
                    </q-table>
                  </q-card>
                </div>
              </div>
            </div>
          </div>

          <!-- Performance Section -->
          <div class="col-4 q-pl-md">

            <q-btn-group unelevated>
              <q-btn label="Performance" :style="{
                'text-transform': 'none',
                'font-size': '16px',
                color: !isPerformanceActive ? '#585858' : '',
              }" :class="{ activeButton: isPerformanceActive }" @click="activatePerformance" />
              <q-btn label="Active Sprint" :style="{
                'text-transform': 'none',
                'font-size': '16px',
                color: !isSprintActive ? '#585858' : '',
              }" :class="{ activeButton: isSprintActive }" @click="activateSprint" />
            </q-btn-group>
            <div v-if="isSprintActive">
              <div class="logo-page">Sprint 1</div>
              <div class="font-active">
                <q-expansion-item switch-toggle-side v-for="(item, index) in sprintItems" :key="index"
                  :label="item.story" v-model:expanded="item.expanded">
                  <q-item v-for="(task, idx) in item.tasks" :key="idx">
                    <q-item-section class="q-ml-xl">{{ task.name }}</q-item-section>
                    <q-item-section side>
                      <div class="sketh" style="background-image: url('path/to/avatar1.jpg');"></div>
                    </q-item-section>
                    <q-item-section side>{{ task.progress }}%</q-item-section>
                  </q-item>
                </q-expansion-item>
              </div>
            </div>
            <div v-if="isPerformanceActive">

              <!-- First Card -->
              <div class="row q-mt-s justify-center">
                <div class="col-4">
                  <q-avatar size="150px" :src="topPerformers[1].src" class="q-mb-sm" />
                  <q-card flat bordered class="text-center">
                    <q-card-section>
                      <div>{{ topPerformers[1].name }}</div>
                      <div>{{ topPerformers[1].points }} Pts</div>
                      <div>{{ topPerformers[1].tasks }} Tasks</div>
                    </q-card-section>
                  </q-card>
                </div>
                <div class="col-4 q-mt-s">
                  <q-avatar size="200px" :src="topPerformers[0].src" class="q-mb-sm" />
                  <q-card flat bordered class="text-center bg-warning">
                    <q-card-section>
                      <div>{{ topPerformers[0].name }}</div>
                      <div>{{ topPerformers[0].points }} Pts</div>
                      <div>{{ topPerformers[0].tasks }} Tasks</div>
                    </q-card-section>
                  </q-card>
                </div>
                <div class="col-4">
                  <q-avatar size="150px" :src="topPerformers[2].src" class="q-mb-sm" />
                  <q-card flat bordered class="text-center">
                    <q-card-section>
                      <div>{{ topPerformers[2].name }}</div>
                      <div>{{ topPerformers[2].points }} Pts</div>
                      <div>{{ topPerformers[2].tasks }} Tasks</div>
                    </q-card-section>
                  </q-card>
                </div>
              </div>

              <!-- Other Performers List -->
              <q-list class="q-mt-md">
                <q-item v-for="performer in otherPerformers" :key="performer.name">
                  <q-item-section avatar>
                    <q-avatar :src="performer.src" />
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>{{ performer.name }}</q-item-label>
                    <q-item-label caption>{{ performer.points }} Pts</q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>
            </div>
          </div>
        </div>
      </q-page>
    </q-page-container>
  </q-layout>

  <!-- Page -->
</template>

<script setup>
import { ref } from 'vue'


defineOptions({
  name: 'MainLayout'
});

const currentPage = ref(1)
const totalPages = ref(10)
const totalEntries = ref(100)

const members = [
  // Sample avatar URLs
  'https://dummyjson.com/icon/emilys/128',
  'https://dummyjson.com/icon/johndoe/128'

];

const menu = ref(false)
const selectedTab = ref('Active Sprint')

const columns = ref([
  { name: 'id', align: 'left', label: 'No', field: 'id' },
  { name: 'title', align: 'left', label: 'Title', field: 'title' },
  { name: 'code', align: 'left', label: '# Code', field: 'code' },
  { name: 'type', align: 'left', label: 'Type', field: 'type', sortable: true },
  { name: 'dueDate', align: 'left', label: 'Due Date', field: 'dueDate' },
  { name: 'stakeholders', align: 'left', label: 'Stakeholder', field: 'stakeholders' },
  { name: 'progress', align: 'left', label: 'Progress', field: 'progress' }
]);

const rows = ref([
  {
    id: 1,
    title: 'MES System SPP Department',
    code: 'RQR001',
    type: 'Requirement',
    dueDate: '28 Aug 2024',
    stakeholders: [
      'https://randomuser.me/api/portraits/men/32.jpg',
      'https://randomuser.me/api/portraits/women/44.jpg',
      'https://randomuser.me/api/portraits/men/53.jpg'
    ],
    progress: 90
  },
  {
    id: 2,
    title: 'Boards',
    code: 'RQR002',
    type: 'Requirement',
    dueDate: '29 Aug 2024',
    stakeholders: [
      'https://randomuser.me/api/portraits/women/22.jpg',
      'https://randomuser.me/api/portraits/men/65.jpg'
    ],
    progress: 70
  },
  {
    id: 3,
    title: 'Product Monitoring',
    code: 'RQR003',
    type: 'Requirement',
    dueDate: '30 Aug 2024',
    stakeholders: [
      'https://randomuser.me/api/portraits/men/12.jpg',
      'https://randomuser.me/api/portraits/women/65.jpg'
    ],
    progress: 50
  },
  {
    id: 4,
    title: 'RPA for Simplified Purchasing in SAP',
    code: 'RQR004',
    type: 'Requirement',
    dueDate: '31 Aug 2024',
    stakeholders: [
      'https://randomuser.me/api/portraits/women/65.jpg'
    ],
    progress: 50
  },
  {
    id: 5,
    title: 'ML-Powered Interception of False Calls in PCB Visual Inspection (SMT)',
    code: 'RQR005',
    type: 'Change Request',
    dueDate: '1 Sep 2024',
    stakeholders: [
      'https://randomuser.me/api/portraits/women/65.jpg'
    ],
    progress: 0
  },
  {
    id: 6,
    title: 'Pcb counter using computer vision (SMT)',
    code: 'RQR006',
    type: 'Change Request',
    dueDate: '2 Sep 2024',
    stakeholders: [
      'https://randomuser.me/api/portraits/women/65.jpg'
    ],
    progress: 0
  },
  {
    id: 7,
    title: 'Handover PLC Communication for Battery Cover Inspection',
    code: 'RQR007',
    type: 'Change Request',
    dueDate: '3 Sep 2024',
    stakeholders: [
      'https://randomuser.me/api/portraits/women/65.jpg'
    ],
    progress: 0
  },
  {
    id: 8,
    title: 'RPA for Simplified HR in HRMS and Government Portal',
    code: 'RQR008',
    type: 'Issue',
    dueDate: '4 Sep 2024',
    stakeholders: [
      'https://randomuser.me/api/portraits/women/65.jpg'
    ],
    progress: 0
  },
  {
    id: 9,
    title: 'Controller dehumidifier iot (SMT)',
    code: 'RQR009',
    type: 'Issue',
    dueDate: '5 Sep 2024',
    stakeholders: [
      'https://randomuser.me/api/portraits/women/65.jpg'
    ],
    progress: 0
  },
  {
    id: 10,
    title: 'PM Tools Phase 4 (Agile)',
    code: 'RQR010',
    type: 'Issue',
    dueDate: '6 Sep 2024',
    stakeholders: [
      'https://randomuser.me/api/portraits/women/65.jpg'
    ],
    progress: 0
  },
]);

const typeColor = (type) => {
  switch (type) {
    case 'Requirement':
      return 'purple';
    case 'Change Request':
      return 'orange';
    case 'Issue':
      return 'red';
    default:
      return 'grey';
  }
};

const topPerformers = [
  { name: 'Alex Sirait', points: 251, tasks: 232, src: 'avatar_top1.png' },
  { name: 'Febby Fakhrian', points: 230, tasks: 199, src: 'avatar_top2.png' },
  { name: 'Jassy Lee', points: 200, tasks: 200, src: 'avatar_top3.png' }
]

const otherPerformers = [
  { name: 'Aryo Yudho', points: 190, src: 'avatar4.png' },
  { name: 'Alfaturr Rahman', points: 180, src: 'avatar5.png' },
  { name: 'Margareth Meylia', points: 170, src: 'avatar6.png' },
  // More performers...
]
const btnToggleOptions = [
  { label: 'Active Sprint', value: 'sprint' },
  { label: 'Performance', value: 'performance' }
]


const statuses = ref([
  { label: "Preparation", color: "#e0e0e0" },
  { label: "Planning", color: "#42a5f5" },


]);

const isSprintActive = ref(true);
const isPerformanceActive = ref(false);

const activatePerformance = () => {
  isPerformanceActive.value = true;
  isSprintActive.value = false;
};

const activateSprint = () => {
  isPerformanceActive.value = false;
  isSprintActive.value = true;
};

const tableColumns = [
  { name: 'no', label: 'No', align: 'left', field: 'no' },
  { name: 'title', label: 'Title', align: 'left', field: 'title' },
]

const sprintItems = [
  {
    story: 'Story: Fitur Login',
    expanded: true,
    tasks: [
      { name: '1. BE-Service API Login', avatar: members['picture'], progress: 90 },
      { name: '2. BE-Service Integrasi PM Tools', avatar: members['picture'], progress: 90 },
      { name: '3. FE-Form Login', avatar: members['picture'], progress: 90 },
    ]
  },
  {
    story: 'Story: Fitur Profil',
    expanded: true,
    tasks: [
      { name: '1. UI-Page Profil', avatar: members[0], progress: 90 },
      { name: '2. UI-Page Project Listing', avatar: members[0], progress: 90 },
    ]
  },
  {
    story: 'Story: Fitur Boards',
    expanded: true,
    tasks: [
      { name: '1. UI-Page Board Pre Development', avatar: members[0], progress: 90 },
      { name: '2. UI-Page Board Development', avatar: members[0], progress: 90 },
    ]
  },
  {
    story: 'Story: Project Listing',
    expanded: true,
    tasks: [
      { name: '1. FE-Page Project Listing', avatar: members[0], progress: 90 },
      { name: '2. BE-Integrasi Project Listing', avatar: members[0], progress: 90 },
    ]
  },
  {
    story: 'Story: Product Monitoring',
    expanded: true,
    tasks: [
      { name: '1. FE-Product Monitoring', avatar: members[0], progress: 90 },
      { name: '2. BE-Integrasi Product Monitoring', avatar: members[0], progress: 90 },
      { name: '3. UI-Page Common Board', avatar: members[0], progress: 90 },
      { name: '4. FE-Page Testing Scripts', avatar: members[0], progress: 90 },
    ]
  },
  // ... (other sprint items)
]

const columns_performance = ref([
  { name: 'rank', align: 'left', label: 'Rank', field: 'rank', sortable: true },
  { name: 'avatar', align: 'left', label: 'Avatar', field: 'avatar', sortable: true },
  { name: 'name', align: 'left', label: 'Name', field: 'name', sortable: true },
  { name: 'pts', align: 'right', label: 'Pts', field: 'pts', sortable: true },
  { name: 'task', align: 'right', label: 'Task', field: 'task', sortable: true }
]);

const rows_performance = ref([
  {
    rank: 4,
    name: 'Aryo Yudho',
    pts: 190,
    task: 235
  },
  {
    rank: 5,
    name: 'Alfattur Rahman',
    avatar: 'https://cdn.quasar.dev/img/avatar1.jpg',
    pts: 180,
    task: 200
  },
  {
    rank: 6,
    name: 'Margareth Meylia',
    pts: 170,
    task: 235
  },
  {
    rank: 7,
    name: 'Steven Lim',
    pts: 160,
    task: 199
  },
  {
    rank: 8,
    name: 'Deni Andrian',
    avatar: 'https://cdn.quasar.dev/img/avatar3.jpg',
    pts: 155,
    task: 170
  },
  {
    rank: 9,
    name: 'Vincent',
    pts: 155,
    task: 180
  },
  {
    rank: 10,
    name: 'Muhamad Raffi',
    avatar: 'https://cdn.quasar.dev/img/avatar4.jpg',
    pts: 140,
    task: 235
  },
  {
    rank: 11,
    name: 'Muhammad Chandra',
    avatar: 'https://cdn.quasar.dev/img/avatar5.jpg',
    pts: 130,
    task: 200
  },
  {
    rank: 12,
    name: 'Febri Dwi',
    pts: 125,
    task: 150
  },
  {
    rank: 13,
    name: 'Achmad Budi',
    avatar: 'https://cdn.quasar.dev/img/avatar6.jpg',
    pts: 125,
    task: 160
  },
  {
    rank: 14,
    name: 'Joshua Christoper',
    pts: 125,
    task: 170
  }
]);

const initialPagination = {
  rowsPerPage: 10
  // rowsNumber: xx if getting data from a server
}
</script>

<style scoped>
.header-align {
  display: flex;
  align-content: center;
  justify-content: center;
  flex-direction: column;
}

.logo-title {
  margin-top: auto;
  font-size: 15px;
  font-weight: bold;
}

.logo-subtitle {
  margin-top: -4px;
  font-size: 11px;
}

.title-page {
  margin-top: -6px;
  font-size: 11px;
  margin-bottom: -17px;
}

.card-custom {
  display: flex;
  justify-content: center;
  flex-direction: row;
  align-items: center;
  gap: 20px;
  margin-right: 30px;
}

.text-agile {
  font-weight: bold;
}

.text-cora {
  font-weight: bold;
}

.text-plant {
  font-weight: bold;
}

.card-table {

  width: 925px;
  margin-bottom: 100px;
}

.logo-page-container {
  display: flex;
  align-items: center;
  gap: 910px;
  /* Jarak antara teks dan tombol */
}

.q-pagination {
  display: flex;
  align-items: center;
  gap: 8px;
}

/* .btnagile {
  margin-left: 1px;
} */

.btncora {
  margin-left: 171px;
}

.btnplant {
  margin-left: 60px;
}

.progress-and-members {
  display: flex;
  align-items: center;
  gap: 10px;
  /* Space between the circular progress and the members section */
}

.progress-container {
  flex-shrink: 0;
  /* Prevents the circular progress from shrinking */
}

.members-container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.epic-container {
  display: flex;
  align-items: center;
  gap: 16px;
  /* Adjust space between the label and the button */
}

.font-active {
  font-size: 11px;
}

.logo-page {
  font-size: 15px;
  /* Adjust size as need`ed */
  font-weight: bold;
  /* Optional: Adjust weight if needed */
}

.header-container {
  display: flex;
  align-items: center;
  gap: 16px;
  /* Adjust the space between the label and the buttons */
}

.button-group {
  display: flex;
  gap: 8px;
  padding: 1px 1px;
  /* Adjust the space between the buttons */

}

/* .button-search {
  margin-left: 1090px;
} */

/* .card-perform {
  height: 980px;
  width: 600px;
} */

.avatar-container {
  display: flex;
  align-items: center;
}

.avatar-group {
  display: flex;
  position: relative;
}

.avatar {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background-color: #ccc;
  background-size: cover;
  background-position: center;
  border: 2px solid #fff;
  margin-left: -8px;
  font-size: 10px;
  text-align:center;
}

.more-count {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background-color: #ccc;
  background-size: cover;
  background-position: center;
  border: 2px solid #fff;
  margin-left: -8px;
  font-size: 10px;
  text-align:center;
}

.activeButton {
  border-bottom: 1px solid #cd202e;
  color: #cd202e;
}

.sketh {
  display: flex;
  position: relative;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background-color: #ccc;
  background-size: cover;
  background-position: center;
  border: 2px solid #fff;
  margin-left: -8px;
}

.col-4 {
  border: '1px solid #CED3D7'
}

.text-left {
  font-size: 11px;
}

.text-right {
  font-size: 11px;
}
</style>
