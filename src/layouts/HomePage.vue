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
                              <q-item-section side>
                                <q-icon name="error" />
                              </q-item-section>
                              <q-item-section>View Project</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="open_in_new" />
                              </q-item-section>
                              <q-item-section>Open Board</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="share" />
                              </q-item-section>
                              <q-item-section>Share</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="autorenew" />
                              </q-item-section>
                              <q-item-section>Planning</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="edit_note" />
                              </q-item-section>
                              <q-item-section>Activities</q-item-section>
                            </q-item>
                          </q-list>
                        </q-menu>
                      </q-btn>
                    </div>
                    <div class="progress-and-members">
                      <div class="progress-container">
                        <q-circular-progress size="100px" font-size="15px" :value="40" color="pink" track-color="grey-3"
                          show-value>
                          <div class="centering">
                            <div class="text-caption">Progress</div>
                            <div class="text-weight-bold">40%</div>
                          </div>
                        </q-circular-progress>
                      </div>
                      <div class="members-container">
                        <div>15 Members</div>
                        <div class="avatar-container">
                          <div class="avatar-group">
                            <div class="avatar" style="background-image: url('src/assets/aura.png');">
                            </div>
                          </div>
                          <div class="avatar" style="background-image: url('src/assets/aura.png');">
                          </div>
                          <div class="avatar" style="background-image: url('src/assets/aura.png');">
                          </div>
                          <div class="avatar" style="background-image: url('src/assets/aura.png');">
                          </div>
                          <div class="more-count">+10</div>
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
                              <q-item-section side>
                                <q-icon name="error" />
                              </q-item-section>
                              <q-item-section>View Project</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="open_in_new" />
                              </q-item-section>
                              <q-item-section>Open Board</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="share" />
                              </q-item-section>
                              <q-item-section>Share</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="autorenew" />
                              </q-item-section>
                              <q-item-section>Planning</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="edit_note" />
                              </q-item-section>
                              <q-item-section>Activities</q-item-section>
                            </q-item>
                          </q-list>
                        </q-menu>
                      </q-btn>
                    </div>
                    <div class="progress-and-members">
                      <div class="progress-container">
                        <q-circular-progress size="100px" font-size="15px" :value="90" color="green"
                          track-color="grey-3" show-value>
                          <div class="centering">
                            <div class="text-caption">Progress</div>
                            <div class="text-weight-bold">90%</div>
                          </div>
                        </q-circular-progress>
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
                          <q-list dense>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="error" />
                              </q-item-section>
                              <q-item-section>View Project</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="open_in_new" />
                              </q-item-section>
                              <q-item-section>Open Board</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="share" />
                              </q-item-section>
                              <q-item-section>Share</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="autorenew" />
                              </q-item-section>
                              <q-item-section>Planning</q-item-section>
                            </q-item>
                            <q-item clickable v-close-popup>
                              <q-item-section side>
                                <q-icon name="edit_note" />
                              </q-item-section>
                              <q-item-section>Activities</q-item-section>
                            </q-item>
                          </q-list>
                        </q-menu>
                      </q-btn>
                    </div>
                    <div class="progress-and-members">
                      <div class="progress-container">
                        <q-circular-progress size="100px" font-size="15px" :value="70" color="yellow"
                          track-color="grey-3" show-value>
                          <div class="centering">
                            <div class="text-caption">Progress</div>
                            <div class="text-weight-bold">70%</div>
                          </div>
                        </q-circular-progress>
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
      background-color: #f9dbf6;
      color: black;
      border-radius: 15%;
      padding: 3px 6px;
      font-size: 12px;
    ">
                    20
                  </span>
                  <q-btn class="button-search" flat icon="search" label="Search" :style="{
                    'text-transform': 'none',
                    'font-size': '13px',
                    'border-radius': '11px',
                    'padding-left': '15px',
                    'align-items': 'center',
                    'margin-left': '619px',
                    'padding': '3px 3px',
                    height: '20px',
                    border: '1px solid #CED3D7',
                    color: '#585858',
                    width: '240px',
                  }" />
                </div>
                <div class="row q-gutter-md" style="margin-top: 2px;">
                  <q-card class="card-table">

                    <div class="table-pagination-container">
                      <q-table :rows="rows" :columns="columns" flat table-style="table-layout: auto;"
                        :pagination="initialPagination" hide-bottom>
                        <template v-slot:header="props">
                          <q-tr :props="props">
                            <q-th v-for="col in props.cols" :key="col.name" :props="props">
                              <!-- Add icon conditionally to specific columns like 'title', 'code', 'dueDate' -->
                              <q-icon size="xs" v-if="col.field === 'title'" name="sticky_note_2" />
                              <q-icon size="xs" v-if="col.field === 'code'" name="tag" />
                              <q-icon size="xs" v-if="col.field === 'type'" name="sticky_note_2" />
                              <q-icon size="xs" v-if="col.field === 'dueDate'" name="calendar_month" />
                              <q-icon size="xs" v-if="col.field === 'stakeholders'" name="group" />
                              <q-icon size="xs" v-if="col.field === 'progress'" name="percent" />

                              {{ col.label }}
                            </q-th>
                          </q-tr>
                        </template>
                        <template v-slot:body-cell="props">
                          <q-td :props="props">
                            <div v-if="props.col.field === 'progress'" class="q-mt-xs flex items-center">
                              <span>{{ props.row.progress }}%</span>
                              <q-icon name="more_vert" class="q-ml-xl cursor-pointer absolute"
                                @click="onIconClick(props.row)" />
                              <q-menu>
                                <q-list dense style="min-width: 200px">
                                  <q-item clickable v-close-popup>
                                    <q-item-section side>
                                      <q-icon name="visibility" />
                                    </q-item-section>
                                    <q-item-section>Detail</q-item-section>
                                  </q-item>
                                  <q-item clickable v-close-popup>
                                    <q-item-section side>
                                      <q-icon name="share" />
                                    </q-item-section>
                                    <q-item-section>Share</q-item-section>
                                  </q-item>
                                </q-list>
                              </q-menu>
                            </div>
                            <div v-else-if="props.col.field === 'stakeholders'" class="q-gutter-xs flex">
                              <div class="avatar" style="background-image: url('src/assets/aura.png');"></div>
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
                    </div>
                  </q-card>
                  <div class="pagination-container_page q-px-xl">
                    <div style="width: 100%;" class="q-mb-lg flex items-center justify-between">
                      <div class="q-mr-lg">Showing 1 to 10 of 20 entries</div>
                      <div class="flex items-center">
                        <q-btn flat label="Previous" @click="prevPage" :disabled="current === 1" />
                        <q-pagination class="q-mx-sm" v-model="current" color="black" :max="10" :max-pages="6"
                          :boundary-numbers="false" />
                        <q-btn flat label="Next" @click="nextPage" :disabled="current === 10" />
                      </div>
                    </div>
                  </div>
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
              <div class="row">
                <div class="logo-page">Sprint 1</div>
                <div class="q-ml-sm text-caption">
                  (1 Agu 2024 - 15 Agu 2024)
                </div>
              </div>
              <div class="font-active">
                <q-expansion-item switch-toggle-side expand-separator v-for="(item, index) in sprintItems" :key="index"
                  :label="item.story" v-model:expanded="item.expanded">
                  <q-item expand-separator v-for="(task, idx) in item.tasks" :key="idx">
                    <q-item-section class="q-ml-xl">{{ task.name }}</q-item-section>
                    <q-item-section side>
                      <div class="sketh" style="background-image: url('src/assets/aura.png');"></div>
                    </q-item-section>
                    <q-item-section side>{{ task.progress }}%</q-item-section>
                  </q-item>
                </q-expansion-item>
              </div>
            </div>
            <div v-if="isPerformanceActive">


              <div class="podium row justify-center items-end">

                <!-- Second Place -->
                <div class="podium-step col-3 column items-center">
                  <!-- Name and Image above the podium -->
                  <!-- <q-icon name="fas fa-medal" class="silver medal-icon" /> -->
                  <div class="podium-avatar">
                    <div class="centering_div">
                      <q-img class="medali-perak" src="src/assets/perak.svg" />
                      <q-img src="src/assets/aura.png" style="border-radius: 50%; width: 80px; height: 80px;" />
                    </div>
                    <p class="small-name">Febby Fakhrian</p>
                  </div>

                  <!-- Podium block with score -->
                  <div class="podium-second">
                    <div class="rank-number">2</div>
                    <div class="score">
                      <q-chip class="small-pts">230 Pts</q-chip>
                      <q-chip class="small-pts">199 Task</q-chip>
                    </div>
                  </div>
                </div>

                <!-- First Place -->
                <div class="podium-step col-3 column items-center">
                  <!-- Name and Image above the podium -->
                  <div class="podium-avatar">
                    <div class="centering_div">
                    <q-img class="medali-perak" src="src/assets/medali1.svg" />
                    <q-img src="src/assets/aura.png" style="border-radius: 50%; width: 80px; height: 80px;" />
                  </div>
                    <p class="small-name">Alex Sirait</p>
                  </div>

                  <!-- Podium block with score -->
                  <div class="podium-first">
                    <div class="rank-number">1</div>
                    <div class="score">
                      <q-chip class="small-pts">251 Pts</q-chip>
                      <q-chip class="small-pts">232 Task</q-chip>
                    </div>
                  </div>
                </div>

                <!-- Third Place -->
                <div class="podium-step col-3 column items-center">
                  <!-- Name and Image above the podium -->
                  <div class="podium-avatar">
                    <div class="centering_div">
                    <q-img class="medali-perak" src="src/assets/medali3.svg" />
                    <q-img src="src/assets/aura.png" style="border-radius: 50%; width: 80px; height: 80px;" />
                  </div>
                    <p class="small-name">Jassy Lee</p>
                  </div>

                  <!-- Podium block with score -->
                  <div class="podium-third">
                    <q-icon name="medal" class="bronze" style="font-size: 40px;"></q-icon>
                    <div class="rank-number">3</div>
                    <div class="score">
                      <q-chip class="small-pts">200 Pts</q-chip>
                      <q-chip class="small-pts">200 Task</q-chip>
                    </div>
                  </div>
                </div>

              </div>

              <!-- Rankings Table -->
              <q-table :rows="rankingData" :columns="columnsrank" row-key="rank" flat class="q-my-md"
                :pagination="initialPagination" hide-bottom hide-header>
                <template v-slot:body="props">
                  <q-tr :props="props">
                    <q-td v-for="col in props.cols" :key="col.name" :props="props">
                      <template v-if="col.name === 'avatar'">
                        <q-img :src="props.row.avatar" style="border-radius: 50%; width: 32px; height: 32px;" />
                      </template>
                      <template v-else>
                        <div :style="{
                          backgroundColor: col.name === 'points' ? '#e6d7fc' : (col.name === 'tasks' ? '#d0e9ff' : 'transparent'),
                          color: 'black',  /* Optional: change text color for better contrast */
                          padding: '1px', /* Optional: add some padding */
                          borderRadius: '4px' /* Optional: add some border radius */
                        }">
                          {{ props.row[col.field] }}
                        </div>
                      </template>
                    </q-td>
                  </q-tr>
                </template>
              </q-table>
            </div>
          </div>
        </div>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'


defineOptions({
  name: 'HomePage'
});

const current = ref(5)
const prevPage = () => {
  if (current.value > 1) {
    current.value--
  }
}

const nextPage = () => {
  if (current.value < 10) { // Adjust max page number as needed
    current.value++
  }
}
const totalPages = ref(10)
const totalEntries = ref(100)

const members = [
  // Sample avatar URLs
  'https://dummyjson.com/icon/emilys/128',
  'https://dummyjson.com/icon/johndoe/128'

];

const menu = ref(false)
// const selectedTab = ref('Active Sprint')

const columnsrank = [
  { name: 'rank', field: 'rank', align: 'center' },
  { name: 'avatar', field: 'avatar', align: 'center', label: 'Avatar', style: 'width: 50px;' },
  { name: 'name', field: 'name', align: 'left' },
  { name: 'points', field: 'points', align: 'center' },
  { name: 'tasks', field: 'tasks', align: 'center' },
]

const rankingData = [
  { rank: 4, avatar: 'src/assets/aura.png', name: 'Aryo Yudho', points: '190 Pts', tasks: '235 Task' },
  { rank: 5, avatar: 'src/assets/aura.png', name: 'Alfaturr Rahman', points: '180 Pts', tasks: '200 Task' },
  { rank: 6, avatar: 'src/assets/aura.png', name: 'Margareth Meylia', points: '170 Pts', tasks: '235 Task' },
  { rank: 7, avatar: 'src/assets/aura.png', name: 'Steven Lim', points: '160 Pts', tasks: '199 Task' },
  { rank: 8, avatar: 'src/assets/aura.png', name: 'Deni Andrian', points: '155 Pts', tasks: '170 Task' },
  { rank: 9, avatar: 'src/assets/aura.png', name: 'Vincent', points: '155 Pts', tasks: '180 Task' },
  { rank: 10, avatar: 'src/assets/aura.png', name: 'Muhammad Raffi', points: '140 Pts', tasks: '235 Task' },
  { rank: 11, avatar: 'src/assets/aura.png', name: 'Muhammad Chandra', points: '140 Pts', tasks: '150 Task' },
  { rank: 12, avatar: 'src/assets/aura.png', name: 'Febri Dwi', points: '140 Pts', tasks: '150 Task' },
  { rank: 13, avatar: 'src/assets/aura.png', name: 'Achmad Budi', points: '125 Pts', tasks: '170 Task' },
  { rank: 14, avatar: 'src/assets/aura.png', name: 'Joshua Christoper', points: '125 Pts', tasks: '170 Task' },
]

const columns = ref([
  { name: 'id', align: 'left', label: 'No', field: 'id' },
  { name: 'title', align: 'left', label: 'Title', field: 'title' },
  { name: 'code', align: 'left', label: 'Code', field: 'code' },
  { name: 'type', align: 'left', label: 'Type', field: 'type' },
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
      'src/assets/aura.png',
      'src/assets/aura.png',
      'src/assets/aura.png'
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
    case 'pts':
      return 'purple';
    case 'task':
      return 'blue';
  }
};

const topPerformers = [
  { name: 'Alex Sirait', points: 251, tasks: 232, src: 'avatar_top1.png' },
  { name: 'Febby Fakhrian', points: 230, tasks: 199, src: 'avatar_top2.png' },
  { name: 'Jassy Lee', points: 200, tasks: 200, src: 'avatar_top3.png' }
]

const otherPerformers = [
  { name: 'Aryo Yudho', points: 190, src: 'src/assets/aura.png' },
  { name: 'Alfaturr Rahman', points: 180, src: 'src/assets/aura.png' },
  { name: 'Margareth Meylia', points: 170, src: 'src/assets/aura.png' },
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
    avatar: 'src/assets/aura.png',
    name: 'Aryo Yudho',
    pts: 190,
    task: 235
  },
  {
    rank: 5,
    avatar: 'src/assets/aura.png',
    name: 'Alfattur Rahman',
    pts: 180,
    task: 200
  },
  {
    rank: 6,
    avatar: 'src/assets/aura.png',
    name: 'Margareth Meylia',
    pts: 170,
    task: 235
  },
  {
    rank: 7,
    avatar: 'src/assets/aura.png',
    name: 'Steven Lim',
    pts: 160,
    task: 199
  },
  {
    rank: 8,
    avatar: 'src/assets/aura.png',
    name: 'Deni Andrian',
    pts: 155,
    task: 170
  },
  {
    rank: 9,
    avatar: 'src/assets/aura.png',
    name: 'Vincent',
    pts: 155,
    task: 180
  },
  {
    rank: 10,
    avatar: 'src/assets/aura.png',
    name: 'Muhamad Raffi',
    pts: 140,
    task: 235
  },
  {
    rank: 11,
    avatar: 'src/assets/aura.png',
    name: 'Muhammad Chandra',
    pts: 130,
    task: 200
  },
  {
    rank: 12,
    avatar: 'src/assets/aura.png',
    name: 'Febri Dwi',
    pts: 125,
    task: 150
  },
  {
    rank: 13,
    avatar: 'src/assets/aura.png',
    name: 'Achmad Budi',
    pts: 125,
    task: 160
  },
  {
    rank: 14,
    avatar: 'src/assets/aura.png',
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
  padding-top: 20px;
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

  width: 939px;
  margin-left: 33px;

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

.centering {
  width: 100%;
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  align-items: center;
  gap: 10px;
}

.members-container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  font-size: 12px;
}

.epic-container {
  display: flex;
  align-items: center;
  gap: 16px;

  /* Adjust space between the label and the button */
}

.font-active {
  font-size: 12px;
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
  margin-left: 619px
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
  text-align: center;
}

.more-count {
  display: flex;
  justify-content: center;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background-color: #ccc;
  border: 2px solid #fff;
  margin-left: -8px;
  font-size: 10px;
  font-weight: bold;
  align-items: center;
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

.podium-container {
  display: flex;
  align-items: flex-end;
}

.podium {
  text-align: center;
  padding: 10px;
}

.podium-1 {
  background-color: #ffd700;
  width: 120px;
  height: 200px;
}

.podium-2 {
  background-color: #c0c0c0;
  width: 100px;
  height: 170px;
}

.podium-3 {
  background-color: #cd7f32;
  width: 100px;
  height: 150px;
}

.podium-image {
  width: 80px;
  height: 80px;
  border-radius: 50%;
}

.podium-info {
  margin-top: 10px;
}

.podium-name {
  font-size: 1.2em;
  font-weight: bold;
}

.podium-stats {
  font-size: 1em;
  color: #666;
}

.q-table {
  width: 80%;
}

.popup {
  display: none;
  position: absolute;
  bottom: 100%;
  left: 50%;
  transform: translateX(-50%);
  background-color: black;
  color: white;
  padding: 5px 10px;
  border-radius: 5px;
  font-size: 12px;
  white-space: nowrap;
  opacity: 0;
  transition: opacity 0.3s;
}

/* Show popup on hover */
.avatar:hover .popup {
  display: block;
  opacity: 1;
}

.podium-step {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

.podium-avatar {
  text-align: center;
  margin-top: 20px;
}

.centering_div{
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  align-items: center;
  gap: 7px;
}

.podium {
  height: 350px;
}

.podium-second {
  background-color: grey;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 145px;
  width: 120px;
}

.podium-first {
  background-color: #f9c74f;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 170px;
  width: 121px;
}

.podium-third {
  background-color: orange;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 130px;
  width: 120px;
}


.gold {
  color: gold;
}

.silver {
  color: silver;
}

.bronze {
  color: #cd7f32;
}

.score {
  display: flex;
  flex-direction: column;
  margin-bottom: 20px;
  font-size: 8px;
}

h3 {
  margin: 10px 0;
}

.small-name {
  font-size: 12px;
  margin-bottom: 5px;
}

.small-pts {
  font-size: 10px;
  margin-top: auto;
}

.img-podium {
  margin-top: 30px;
}

.rank-number {
  font-size: 30px;
  margin-bottom: 10px;
  color: #fff;
}

.medal-icon {
  position: absolute;
  top: -20px;
  left: 50%;
  transform: translateX(-50%);
  font-size: 30px;
}

.table-pagination-container {
  position: relative;
}


.pagination-container_page {
  display: flex;
  justify-content: center;
  width: 100%;
}

.pagination-container {
  position: absolute;
  bottom: 0;
  right: 0;
  width: 100%;
  display: flex;
  justify-content: flex-end;
  margin-left: 100px;
}

.paginat {
  margin-left: 690px;
}

.q-btn {
  text-transform: none;
}

.text-center {
  text-align: center;
}

.medali-perak {
  width: 30px;
  height: 30px;
}
</style>
