<!-- Header -->
<template>
  <q-layout view="hHh lpR fFf">
    <q-header reveal elevated class="bg-negative text-white">
      <q-toolbar>
        <q-btn flat round dense icon="menu" class="q-mr-sm" />
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
                <div class="text-h6 text-weight-light">
                  <span class="logo-title">Febby</span>
                </div>
                <div class="logo-subtitle">
                  Product Designer
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
        <div class="q-gutter-md">
          <div class="logo-page">Project Summary</div>
          <div class="title-page">
            Good Morning, Febby Syaiful Pratama
          </div>
          <div class="row q-gutter-md">
            <q-card class="q-pa-md card-custom">
              <div class="text-h6">Project Management Agile Board 2.0</div>
              <q-circular-progress :value="40" size="80px" color="pink" show-value />
              <div>Progress</div>
              <div>15 Members</div>
              <q-avatar-group :max="10">
                <q-avatar v-for="member in members" :key="member" :src="member" />
              </q-avatar-group>
            </q-card>
            <q-card class="q-pa-md card-custom">
              <div class="text-h6">CORA 2.0</div>
              <q-circular-progress :value="90" size="80px" color="green" show-value />
              <div>Progress</div>
              <div>15 Members</div>
              <q-avatar-group :max="10">
                <q-avatar v-for="member in members" :key="member" :src="member" />
              </q-avatar-group>
            </q-card>
            <q-card class="q-pa-md card-custom">
              <div class="text-h6">Plant Maintenance Phase 3</div>
              <q-circular-progress :value="70" size="80px" color="yellow" show-value />
              <div>Progress</div>
              <div>15 Members</div>
              <q-avatar-group :max="10">
                <q-avatar v-for="member in members" :key="member" :src="member" />
              </q-avatar-group>
            </q-card>
          </div>

          <!-- Epic Table Section -->
          <div class="logo-page-container">
            <div class="logo-page">Epic</div>
            <q-btn flat icon="search" label="Search" class="custom-btn" :style="{
              'text-transform': 'none',
              'font-size': '16px',
              'border-radius': '12px',
              'padding-left': '15px',
              'align-items': 'center',
              height: '20px',
              border: '1px solid #CED3D7',
              color: '#585858',
              width: '300px',
            }" />
          </div>
          <q-card flat bordered class="q-mt-md">
            <q-table rows-per-page-options="[10, 20, 50]" :rows="rows" :columns="columns" row-key="no"
              separator="horizontal">
              <template v-slot:body-cell-progress="props">
                <q-linear-progress :value="props.row.progress" color="blue" track-color="grey-3" />
              </template>
              <template v-slot:body-cell-stakeholder="props">
                <q-avatar-group :max="6">
                  <q-avatar v-for="(avatar, index) in props.row.stakeholder" :key="index" :src="avatar" />
                </q-avatar-group>
              </template>
            </q-table>
          </q-card>

          <!-- Performance Section -->
          <q-card flat bordered class="q-mt-md">
            <q-card-section>
              <div class="text-h6">Performance</div>
              <q-btn-toggle v-model="selectedTab" unelevated rounded toggle-color="primary"
                :options="btnToggleOptions" />
              <q-table :rows="rows" :columns="tableColumns" />
            </q-card-section>
            <q-card-section>
              <q-list bordered separator>
                <q-expansion-item v-for="(item, index) in sprintItems" :key="index" :label="item.story"
                  v-model:expanded="item.expanded">
                  <q-item v-for="(task, idx) in item.tasks" :key="idx">
                    <q-item-section>{{ task.name }}</q-item-section>
                    <q-item-section side>
                      <q-avatar size="32px" :src="task.avatar" />
                    </q-item-section>
                    <q-item-section side>{{ task.progress }}%</q-item-section>
                  </q-item>
                </q-expansion-item>
              </q-list>
            </q-card-section>
          </q-card>
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

const members = [
  // Sample avatar URLs
  'https://dummyjson.com/image/i/products/1/1.jpg',
  'https://dummyjson.com/image/i/products/2/1.jpg',
  'https://dummyjson.com/image/i/products/3/1.jpg'
]

const rows = [
  {
    no: 1,
    title: 'MES System SPP Department',
    code: 'RQR001',
    type: 'Requirement',
    dueDate: '28 Aug 2024',
    stakeholder: members,
    progress: 90
  },
  // ... (other rows)
]

const columns = [
  { name: 'no', required: true, label: 'No', align: 'left', field: 'no' },
  { name: 'title', label: 'Title', align: 'left', field: 'title' },
  { name: 'code', label: 'Code', align: 'left', field: 'code' },
  { name: 'type', label: 'Type', align: 'left', field: 'type' },
  { name: 'dueDate', label: 'Due Date', align: 'left', field: 'dueDate' },
  { name: 'stakeholder', label: 'Stakeholder', align: 'center', field: 'stakeholder' },
  { name: 'progress', label: 'Progress', align: 'center', field: 'progress' }
]

const selectedTab = ref('Active Sprint')

const btnToggleOptions = [
  { label: 'Active Sprint', value: 'active' },
  { label: 'Completed', value: 'completed' }
]

const tableColumns = [
  { name: 'no', label: 'No', align: 'left', field: 'no' },
  { name: 'title', label: 'Title', align: 'left', field: 'title' },
]

const sprintItems = [
  {
    story: 'Story: Fitur Login',
    expanded: true,
    tasks: [
      { name: 'BE-Service API Login', avatar: members[0], progress: 90 },
      // ... (other tasks)
    ]
  },
  // ... (other sprint items)
]


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
  font-size: 20px;
  font-weight: bold;
}

.logo-subtitle {
  margin-top: -4px;
  font-size: 12px;
}

.logo-page {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 5px;
}

.title-page {
  margin-top: -4px;
  font-size: 12px;
}

.card-custom {
  height: 200px;
  width: 400px;
}

.logo-page-container {
  display: flex;
  align-items: center;
  gap: 910px;
  /* Jarak antara teks dan tombol */
}
</style>
