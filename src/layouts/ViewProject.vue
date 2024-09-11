<template>
  <q-layout view="hHh lpR fFf" class="hide-scrollbar">
    <q-header reveal elevated class="bg-negative text-white ">
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
      <div class="row">
        <div class="q-pa-md title-container">
          <q-icon name="chevron_left" class="icon" />
          <div class="title-page">
            Project / Detail Project
          </div>
        </div>
        <q-page class="row">
          <!-- Left Panel - Project Detail and Stakeholders -->
          <div class="col-3">
            <q-card class="q-ml-md">
              <q-card-section>
                <div class="header-container">
                  <div class="text-h6">
                    AGL001 - Project Management Agile Board 2.0
                    <span class="icon-group">
                      <q-icon name="delete" title="Edit" size="20px" />
                      <q-icon name="edit" title="Delete" size="20px" />
                    </span>
                  </div>
                </div>
                <div class="text-subtitle2 text-weight-regular">Created by Ali Sadikin (123456), Monday, 19 August 2024,
                  18:02</div>
                <div class="info-container">
                  <q-icon name="calendar_today" class="calendar_month" size="16px" />
                  <span class="date-title">21 Aug 2024 - 28 Aug 2024</span>
                  <q-badge class="q-ml-xs" label="Completed" color="green-11" text-color="black" />
                  <q-badge class="q-ml-xs" label="100%" color="amber-2" text-color="black" />
                </div>
              </q-card-section>
              <q-list bordered />

              <div class="q-pa-md" style="max-width: 512px">
                <q-list bordered class="rounded-borders">
                  <q-expansion-item switch-toggle-side expand-separator label="Information">
                    <q-card>
                      <q-card-section>
                        <!-- Project Type -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle1">Project Type</span>
                          </q-item-section>
                          <q-item-section>
                            <span>IT</span>
                          </q-item-section>
                        </q-item>

                        <!-- Project Description -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle1">Project Description</span>
                          </q-item-section>
                          <q-item-section>
                            <span>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
                              incididunt ut labore et dolore magna aliqua.</span>
                          </q-item-section>
                        </q-item>

                        <!-- Department -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle1">Department</span>
                          </q-item-section>
                          <q-item-section>
                            <span>DOT</span>
                          </q-item-section>
                        </q-item>

                        <!-- Department Owner -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle1">Department Owner</span>
                          </q-item-section>
                          <q-item-section>
                            <span>DOT</span>
                          </q-item-section>
                        </q-item>

                        <!-- Project Manager -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle1">Project Manager</span>
                          </q-item-section>
                          <q-item-section>
                            <div class="row items-center no-wrap">
                              <q-avatar size="xs" class="q-mr-sm">
                                <img src="https://cdn.quasar.dev/img/avatar.png" alt="avatar">
                              </q-avatar>
                              <span>Nurmatias (123456)</span>
                            </div>
                          </q-item-section>
                        </q-item>

                        <!-- Release Date -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle1">Release</span>
                          </q-item-section>
                          <q-item-section>
                            <span>26 Aug 2024 - 30 Aug 2024</span>
                          </q-item-section>
                        </q-item>

                        <!-- Status -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle1">Status</span>
                          </q-item-section>
                          <q-item-section>
                            <q-badge color="green">Completed</q-badge>
                          </q-item-section>
                        </q-item>

                        <!-- Progress -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle1">Progress</span>
                          </q-item-section>
                          <q-item-section>
                            <q-badge color="yellow" text-color="black">100%</q-badge>
                          </q-item-section>
                        </q-item>
                      </q-card-section>
                    </q-card>
                  </q-expansion-item>

                  <q-separator />

                  <q-expansion-item switch-toggle-side expand-separator label="Project Related(10)" icon="add_box">
                    <q-card>
                      <q-card-section>
                        <div class="table-pagination-container">
                          <q-table :rows="rowsSketh" :columns="columnsSketh" flat table-style="table-layout: auto;"
                            :pagination="initialPagination" hide-bottom>
                            <template v-slot:header="props">
                              <q-tr :props="props">
                                <q-th v-for="col in props.cols" :key="col.name" :props="props"
                                  :class="['grey-column', { 'grey-column': col.field === 'no' || col.field === 'name' }]">
                                  <!-- Add icon conditionally to specific columns like 'title', 'code', 'dueDate' -->
                                  <q-icon size="xs" v-if="col.field === 'name'" name="person" />
                                  <q-icon size="xs" v-if="col.field === 'role'" name="personal_injury" />
                                  {{ col.label }}
                                </q-th>
                              </q-tr>
                            </template>
                            <template v-slot:body-cell="props">
                              <q-td :props="props">
                                <div v-if="props.col.field === 'role'"
                                  class="q-mt-xs flex items-center justify-between">
                                  <span>{{ props.row.role }}</span>
                                  <!-- Add the trash icon next to the role -->
                                  <q-icon name="delete" color="black" size="15px" class="cursor-pointer"
                                    @click="onDelete(props.row)" />
                                </div>
                                <div v-else>
                                  {{ props.row[props.col.field] }}
                                </div>
                              </q-td>
                            </template>
                          </q-table>
                        </div>
                      </q-card-section>
                    </q-card>
                  </q-expansion-item>
                </q-list>
              </div>

              <q-card-section>
                <p class="text-h7 text-weight-medium q-my-sm">Content</p>
                <p class="long-text">
                  Like all the great things on earth travelling teaches us by example. Here are some of the most
                  precious
                  lessons I've learned over the years of traveling. Getting used to an entirely different culture can
                  be
                  challenging. While it's also nice to learn about cultures online or from books, nothing comes close
                  to
                  experiencing cultural diversity in person. You learn to appreciate each and every single one of the
                  differences while you become more culturally fluid.</p>
                <p class="long-text">Life doesn't allow us to execute every single plan perfectly. This especially
                  seems to be the case when
                  you travel. You plan it down to every minute with a big checklist. But when it comes to executing
                  it,
                  something always comes up and you're left with your improvising skills. You learn to adapt as you
                  go.
                  Here's how my travel checklist looks now:
                <ul class="q-my-none">
                  <li>buy the ticket</li>
                  <li>start your adventure</li>
                </ul>
                </p>
                <p class="long-text">Going to a new place can be quite terrifying. While change and uncertainty make
                  us scared, traveling
                  teaches us how ridiculous it is to be afraid of something before it happens. The moment you face
                  your
                  fear and see there is nothing to be afraid of, is the moment you discover bliss.</p>
                <p class="long-text">The parties agree to enter into a confidential relationship concerning the
                  disclosure of certain
                  proprietarybusiness property and confidential information <strong>("Confidential
                    Information")</strong>:
                <ol class="q-my-none">
                  <li>Definition of Confidential Information</li>
                  <li>Exclusions from Confidential Information</li>
                  <li>Obligations of Receiving Party</li>
                  <li>Time Periods</li>
                  <li>Relationships</li>
                </ol>
                </p>

                <div class="text-sket">
                  <p class="text-h7 text-weight-medium q-my-sm ">Stakeholders (10)
                    <q-icon name="add_box" size="19px" />
                  </p>
                </div>
                <div class="table-pagination-container">
                  <q-table :rows="rowsSketh" :columns="columnsSketh" flat table-style="table-layout: auto;"
                    :pagination="initialPagination" hide-bottom>
                    <template v-slot:header="props">
                      <q-tr :props="props">
                        <q-th v-for="col in props.cols" :key="col.name" :props="props"
                          :class="['grey-column', { 'grey-column': col.field === 'no' || col.field === 'name' }]">
                          <!-- Add icon conditionally to specific columns like 'title', 'code', 'dueDate' -->
                          <q-icon size="xs" v-if="col.field === 'name'" name="person" />
                          <q-icon size="xs" v-if="col.field === 'role'" name="personal_injury" />
                          {{ col.label }}
                        </q-th>
                      </q-tr>
                    </template>
                    <template v-slot:body-cell="props">
                      <q-td :props="props">
                        <div v-if="props.col.field === 'role'" class="q-mt-xs flex items-center justify-between">
                          <span>{{ props.row.role }}</span>
                          <!-- Add the trash icon next to the role -->
                          <q-icon name="delete" color="black" size="15px" class="cursor-pointer"
                            @click="onDelete(props.row)" />
                        </div>
                        <div v-else>
                          {{ props.row[props.col.field] }}
                        </div>
                      </q-td>
                    </template>
                  </q-table>
                </div>
              </q-card-section>
            </q-card>
          </div>

          <!-- Right Panel - Roadmap Table -->
          <div class="col-9">
            <q-card class="q-ml-md" style="border-color: grey;">
              <q-btn-group unelevated class="q-mt-xs q-ml-xs">
                <q-btn label="Roadmaps" :style="{
                  'text-transform': 'none',
                  'font-size': '12px',
                  color: !isRoadmapsActive ? '#585858' : '',
                }" :class="{ activeButton: isRoadmapsActive }" @click="activateRoadmaps" />
                <q-btn label="Epic" :style="{
                  'text-transform': 'none',
                  'font-size': '12px',
                  color: !isEpicActive ? '#585858' : '',
                }" :class="{ activeButton: isEpicActive }" @click="activateEpic" />
                <q-btn label="Board & Milestone" :style="{
                  'text-transform': 'none',
                  'font-size': '12px',
                  color: !isBoardActive ? '#585858' : '',
                }" :class="{ activeButton: isBoardActive }" @click="activateBoard" />
                <q-btn label="Documentation" :style="{
                  'text-transform': 'none',
                  'font-size': '12px',
                  color: !isDocumActive ? '#585858' : '',
                }" :class="{ activeButton: isDocumActive }" @click="activateDocum" />
                <q-btn label="Activities" :style="{
                  'text-transform': 'none',
                  'font-size': '12px',
                  color: !isActivitiesActive ? '#585858' : '',
                }" :class="{ activeButton: isActivitiesActive }" @click="activateActivities" />
              </q-btn-group>



              <!-- Roadmaps -->
              <div v-if="isRoadmapsActive">
                <div class="row d-flex flex-row justify-between items-center" style="gap: 5px;">
                  <div class="col-2 q-ml-sm q-my-sm ">
                    <q-input color="grey" outlined dense v-model="text" label="Search Roadmaps">
                      <template v-slot:prepend>
                        <q-icon name="search" />
                      </template>
                    </q-input>
                  </div>
                  <div class="col-5 q-my-md q-mr-lg text-right">
                    <q-btn icon="edit" class="text-subtitle2 text-capitalize" color="red-9" label="Add Roadmaps" />
                  </div>
                </div>
                <div class="table-pagination-container">
                  <q-table :rows="rows" :columns="columns" flat table-style="table-layout: auto;"
                    :pagination="initialPagination" hide-bottom>
                    <template v-slot:header="props">
                      <q-tr :props="props">
                        <q-th v-for="col in props.cols" :key="col.name" :props="props"
                          :class="['grey-column', { 'grey-column': col.field === 'no' || col.field === 'title' || col.field === 'dueDate' }]">
                          <!-- Add icon conditionally to specific columns like 'title', 'code', 'dueDate' -->
                          <q-icon size="lg" v-if="col.field === 'no'" name="expand_all" />
                          <q-icon size="xs" v-if="col.field === 'title'" name="sticky_note_2" />
                          <q-icon size="xs" v-if="col.field === 'code'" name="tag" />
                          <q-icon size="xs" v-if="col.field === 'type'" name="sticky_note_2" />
                          <q-icon size="xs" v-if="col.field === 'dueDate'" name="calendar_month" />
                          <q-icon size="xs" v-if="col.field === 'stakeholders'" name="group" />
                          <q-icon size="xs" v-if="col.field === 'progress'" name="percent" />
                          <q-icon size="xs" v-if="col.field === 'totalEpic'" name="expand_circle_down" />

                          {{ col.label }}
                        </q-th>
                      </q-tr>
                    </template>
                    <template v-slot:body-cell="props">
                      <q-td :props="props">
                        <div v-if="props.col.field === 'totalEpic'" class="q-mt-xs flex items-center">
                          <span>{{ props.row.totalEpic }}</span>
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
              </div>


              <!-- Epic -->
              <div v-if="isEpicActive">
                <div class="row d-flex flex-row justify-between items-center" style="gap: 5px;">
                  <div class="col-2 q-ml-sm q-my-sm">
                    <q-input color="grey" outlined dense v-model="text" label="Search Requirement">
                      <template v-slot:prepend>
                        <q-icon name="search" />
                      </template>
                    </q-input>
                    <q-btn flat icon="filter_list" label="Filter" :style="{
                      'text-transform': 'none',
                      'font-size': '16px',
                      'border-radius': '12px',
                      border: '1px solid #CED3D7',
                      color: '#585858',
                    }" />
                  </div>
                  <div class="col-5 q-my-md q-mr-lg text-right">
                    <q-btn icon="edit" class="text-subtitle2 text-capitalize" color="red-9" label="Add Epic" />
                  </div>
                </div>
                <div class="table-pagination-container">
                  <q-table :rows="rowsEpic" :columns="columnsEpic" flat table-style="table-layout: auto;"
                    :pagination="initialPagination" hide-bottom>
                    <template v-slot:header="props">
                      <q-tr :props="props">
                        <q-th v-for="col in props.cols" :key="col.name" :props="props"
                          :class="['grey-column', { 'grey-column': col.field === 'no' || col.field === 'title' || col.field === 'dueDate' }]">
                          <!-- Add icon conditionally to specific columns like 'title', 'code', 'dueDate' -->
                          <q-icon size="lg" v-if="col.field === 'no'" name="expand_all" />
                          <q-icon size="xs" v-if="col.field === 'title'" name="sticky_note_2" />
                          <q-icon size="xs" v-if="col.field === 'code'" name="tag" />
                          <q-icon size="xs" v-if="col.field === 'roadmaps'" name="route" />
                          <q-icon size="xs" v-if="col.field === 'type'" name="sticky_note_2" />
                          <q-icon size="xs" v-if="col.field === 'dueDate'" name="calendar_month" />
                          <q-icon size="xs" v-if="col.field === 'stakeholders'" name="group" />
                          <q-icon size="xs" v-if="col.field === 'progress'" name="percent" />
                          <q-icon size="xs" v-if="col.field === 'status'" name="expand_circle_down" />

                          {{ col.label }}
                        </q-th>
                      </q-tr>
                    </template>
                    <template v-slot:body-cell="props">
                      <q-td :props="props">
                        <div v-if="props.col.field === 'totalEpic'" class="q-mt-xs flex items-center justify-between">
                          <span>{{ props.row.status }}</span>
                          <q-icon name="more_vert" class="cursor-pointer absolute q-ml-sm"
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
                          {{ props.row.status }}
                        </q-badge>
                        <q-badge v-else-if="props.col.field === 'status'" :color="statusColor(props.row.status)"
                          align="center">
                          {{ props.row.status }}
                        </q-badge>
                        <div v-else>
                          {{ props.row[props.col.field] }}
                        </div>
                      </q-td>
                    </template>
                  </q-table>
                </div>
              </div>


              <!-- Board & Milestone -->
              <div v-if="isBoardActive">
                <q-table :rows="rows" :columns="columns" flat class="full-width" row-key="id">
                  <!-- Header Slot -->
                  <template v-slot:header="props">
                    <q-tr :props="props">
                      <q-th v-for="col in props.cols" :key="col.name" :props="props">{{ col.label }}</q-th>
                    </q-tr>
                  </template>

                  <!-- Body Slot -->
                  <template v-slot:body="props">
                    <q-tr :props="props" :class="props.row.expandable ? 'q-row--clickable' : ''"
                      @click="toggleRow(props.row)">
                      <q-td v-for="col in props.cols" :key="col.name" :props="props">
                        <template v-if="col.name === 'no'">
                          <q-icon v-if="props.row.expandable" name="expand_more" @click.stop="toggleRow(props.row)" />
                          {{ props.row.no }}
                        </template>

                        <template v-else-if="col.name === 'progressWeight'">
                          <q-linear-progress :value="props.row.progressWeight / 100" color="blue" size="10px" />
                        </template>

                        <template v-else-if="col.name === 'color'">
                          <q-badge :style="{ backgroundColor: props.row.color }"></q-badge>
                        </template>

                        <template v-else-if="col.name === 'canRetreat'">
                          <q-icon :name="props.row.canRetreat ? 'done' : 'clear'"
                            :color="props.row.canRetreat ? 'green' : 'red'" />
                        </template>

                        <template v-else-if="col.name === 'haveProgress'">
                          <q-icon :name="props.row.haveProgress ? 'done' : 'clear'"
                            :color="props.row.haveProgress ? 'green' : 'red'" />
                        </template>

                        <template v-else-if="col.name === 'pic'">
                          <div class="q-gutter-xs">
                            <q-avatar v-for="avatar in props.row.pic" :key="avatar" size="sm" :src="avatar" />
                            <q-avatar v-if="props.row.picCount" size="sm" label="+"
                              :style="{ backgroundColor: '#ddd' }" />
                          </div>
                        </template>

                        <template v-else>
                          {{ props.row[col.name] }}
                        </template>
                      </q-td>
                    </q-tr>

                    <!-- Expanded Row for Subtasks -->
                    <q-tr v-if="props.row.expanded" class="bg-grey-1">
                      <q-td :colspan="props.cols.length">
                        <q-list>
                          <q-item v-for="subtask in props.row.subtasks" :key="subtask.id">
                            <q-item-section>{{ subtask.title }}</q-item-section>
                          </q-item>
                        </q-list>
                      </q-td>
                    </q-tr>
                  </template>
                </q-table>
              </div>
            </q-card>
          </div>
        </q-page>
      </div>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'

defineOptions({
  name: 'ViewProject'
});



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

const statusColor = (status) => {
  switch (status) {
    case 'Completed':
      return 'green';
    case 'Release':
      return 'blue';
    case 'Draft':
      return 'grey';
  }
};


const stakeholders = ref([
  { id: 1, name: 'Nurmantias (200431)', role: 'Project Manager' },
  { id: 2, name: 'Jassy Lee (200314)', role: 'Project Control' },
  { id: 3, name: 'Jemmy Ng (200341)', role: 'Project Owner' },
  // Add more stakeholders as needed
]);

const isRoadmapsActive = ref(true);
const isEpicActive = ref(false);
const isBoardActive = ref(false);
const isDocumActive = ref(false);
const isActivitiesActive = ref(false);

const activateRoadmaps = () => {
  isRoadmapsActive.value = true;
  isEpicActive.value = false;
  isBoardActive.value = false;
  isDocumActive.value = false;
  isActivitiesActive.value = false;
};

const activateEpic = () => {
  isRoadmapsActive.value = false;
  isEpicActive.value = true;
  isBoardActive.value = false;
  isDocumActive.value = false;
  isActivitiesActive.value = false;
};

const activateBoard = () => {
  isRoadmapsActive.value = false;
  isEpicActive.value = false;
  isBoardActive.value = true;
  isDocumActive.value = false;
  isActivitiesActive.value = false;
};

const activateDocum = () => {
  isRoadmapsActive.value = false;
  isEpicActive.value = false;
  isBoardActive.value = false;
  isDocumActive.value = true;
  isActivitiesActive.value = false;
};

const activateActivities = () => {
  isRoadmapsActive.value = false;
  isEpicActive.value = false;
  isBoardActive.value = false;
  isDocumActive.value = false;
  isActivitiesActive.value = true;
};

const columnsSketh = ref([
  { name: 'id', align: 'left', label: 'No', field: 'id' },
  { name: 'name', align: 'left', label: 'Name', field: 'name' },
  { name: 'role', align: 'left', label: 'Role', field: 'role' },
])

const rowsSketh = ref([
  {
    id: 1,
    name: 'Nurmantias (200431)',
    role: 'Project Manager',
  },
  {
    id: 2,
    name: 'Jassy Lee (200314)',
    role: 'Project Control',
  },
  {
    id: 3,
    name: 'Jemmy Ng (200341)',
    role: 'Project Owner',
  },
  {
    id: 4,
    name: 'Ellin (038720)',
    role: 'Project Owner',
  },
  {
    id: 5,
    name: 'Tia Pasaribu (200344)',
    role: 'User (Planner)',
  },
  {
    id: 6,
    name: 'Kosasi (200344)',
    role: 'User (Store)',
  },
  {
    id: 7,
    name: 'Andria (200344)',
    role: 'Lead (System Analyst)',
  },
  {
    id: 8,
    name: 'Achmad (038720)',
    role: 'Staff (UI/UX Designer)',
  },
  {
    id: 9,
    name: 'Alex (200344)',
    role: 'Staff (Developer)',
  },
  {
    id: 10,
    name: 'Sakti (200341)',
    role: 'Staff (Sr. Developer)',
  },
  {
    id: 11,
    name: 'Rahayu (038720)',
    role: 'Quality Assurance',
  },
  {
    id: 12,
    name: 'Vincent (200431)',
    role: 'Staff (System Integrator)',
  },
]);

const rows = ref([
  {
    id: 1,
    title: 'Job Order',
    code: 'AGL001',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '28 Aug 2024',
    progress: '100%',
    totalEpic: 15,
  },
  {
    id: 2,
    title: 'Master Data Part Number',
    code: 'AGL002',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '29 Aug 2024',
    progress: '100%',
    totalEpic: 10,
  },
  {
    id: 3,
    title: 'Process Model',
    code: 'AGL003',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '30 Aug 2024',
    progress: '100%',
    totalEpic: 20,
  },
  {
    id: 4,
    title: 'Firewall Canban List',
    code: 'AGL004',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '31 Aug 2024',
    progress: '90%',
    totalEpic: 10,
  },
  {
    id: 5,
    title: 'Firewall Request Report',
    code: 'AGL005',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '1 Sep 2024',
    progress: '70%',
    totalEpic: 13,
  },
  {
    id: 6,
    title: 'Detail Firewall Request',
    code: 'AGL006',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '2 Sep 2024',
    progress: '50%',
    totalEpic: 6,
  },
  {
    id: 7,
    title: 'Handover PLC Communication for Battery',
    code: 'AGL007',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '3 Sep 2024',
    progress: '30%',
    totalEpic: 15,
  },
  {
    id: 8,
    title: 'RPA for Simplified HR in HRMS and Government Portal',
    code: 'AGL008',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '4 Sep 2024',
    progress: '0%',
    totalEpic: 13,
  },
  {
    id: 9,
    title: 'Controller dehumidifier iot (SMT)',
    code: 'AGL009',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '5 Sep 2024',
    progress: '0%',
    totalEpic: 20,
  },
  {
    id: 10,
    title: 'PM Tools Phase 4 (Agile) ',
    code: 'AGL010',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '6 Sep 2024',
    progress: '0%',
    totalEpic: 14,
  },
  {
    id: 11,
    title: 'Checksheet',
    code: 'AGL011',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '7 Sep 2024',
    progress: '0%',
    totalEpic: 15,
  },
  {
    id: 12,
    title: 'Asset Equipment Approval Web',
    code: 'AGL012',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '8 Sep 2024',
    progress: '0%',
    totalEpic: 14,
  },
  {
    id: 13,
    title: 'Guets Approval',
    code: 'AGL013',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '9 Sep 2024',
    progress: '0%',
    totalEpic: 16,
  },
  {
    id: 14,
    title: 'E-Kiosk 2.0',
    code: 'AGL014',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '10 Sep 2024',
    progress: '0%',
    totalEpic: 14,
  },
  {
    id: 15,
    title: 'Agile Sprint',
    code: 'AGL015',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '11 Sep 2024',
    progress: '0%',
    totalEpic: 19,
  },
  {
    id: 16,
    title: 'Agile Scrum',
    code: 'AGL016',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '12 Sep 2024',
    progress: '0%',
    totalEpic: 20,
  },
]);

const columns = ref([
  { name: 'id', align: 'left', label: 'No', field: 'id' },
  { name: 'title', align: 'left', label: 'Title', field: 'title' },
  { name: 'code', align: 'left', label: 'Code', field: 'code' },
  { name: 'stakeholders', align: 'left', label: 'Stakeholder', field: 'stakeholders' },
  { name: 'dueDate', align: 'left', label: 'Due Date', field: 'dueDate' },
  { name: 'progress', align: 'left', label: 'Progress', field: 'progress' },
  { name: 'totalEpic', align: 'left', label: 'Total Epic', field: 'totalEpic' },
]);

const initialPagination = {
  rowsPerPage: 16
  // rowsNumber: xx if getting data from a server
}

const rowsEpic = ref([
  {
    id: 1,
    title: 'MES System SPP Departement',
    code: 'RQR001',
    roadmaps: 'Job Order',
    type: "Requirement",
    dueDate: '28 Aug 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '90%',
    status: "Completed",
  },
  {
    id: 2,
    title: 'Boards',
    code: 'RQR002',
    roadmaps: 'Master Data Part Number',
    type: "Requirement",
    dueDate: '29 Aug 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '70%',
    status: "Completed",
  },
  {
    id: 3,
    title: 'Product Monitoring',
    code: 'RQR003',
    roadmaps: 'Process Model',
    type: "Requirement",
    dueDate: '30 Aug 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '50%',
    status: "Completed",
  },
  {
    id: 4,
    title: 'RPA for Simplified Purchasing',
    code: 'RQR004',
    roadmaps: 'Firewall Canban List',
    type: "Requirement",
    dueDate: '31 Aug 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '50%',
    status: "Completed",
  },
  {
    id: 5,
    title: 'ML-Powered Interception of False',
    code: 'RQR005',
    roadmaps: 'Firewall Request Report',
    type: "Requirement",
    dueDate: '1 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Release",
  },
  {
    id: 6,
    title: 'Pcb Counter using computer vision',
    code: 'RQR006',
    roadmaps: 'Detail Firewall Request',
    type: "Change Request",
    dueDate: '2 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Release",
  },
  {
    id: 7,
    title: 'Handover PLC Communication',
    code: 'RQR007',
    roadmaps: 'Handover PLC Communication',
    type: "Change Request",
    dueDate: '3 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Release",
  },
  {
    id: 8,
    title: 'RPA for Simplified HR in HRMS',
    code: 'RQR008',
    roadmaps: 'RPA for Simplified HR in HRMS',
    type: "Change Request",
    dueDate: '4 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Release",
  },
  {
    id: 9,
    title: 'Controller dehumidifier iot (SMT)',
    code: 'RQR009',
    roadmaps: 'Controller dehumidifier iot (SMT)',
    type: "Change Request",
    dueDate: '5 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Release",
  },
  {
    id: 10,
    title: 'PM Tools Phase 4 (Agile) ',
    code: 'AGL010',
    roadmaps: 'PM Tools Phase 4 (Agile)',
    type: "Change Request",
    dueDate: '6 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Release",
  },
  {
    id: 11,
    title: 'Checksheet',
    code: 'AGL011',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '7 Sep 2024',
    progress: '0%',
    totalEpic: 15,
    type: "Issue",
    status: "Draft",
  },
  {
    id: 12,
    title: 'Asset Equipment Approval Web',
    code: 'AGL012',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '8 Sep 2024',
    progress: '0%',
    totalEpic: 14,
    type: "Issue",
    status: "Draft",
  },
  {
    id: 13,
    title: 'Guets Approval',
    code: 'AGL013',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '9 Sep 2024',
    progress: '0%',
    totalEpic: 16,
    type: "Issue",
    status: "Draft",
  },
  {
    id: 14,
    title: 'E-Kiosk 2.0',
    code: 'AGL014',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '10 Sep 2024',
    progress: '0%',
    totalEpic: 14,
    type: "Issue",
    status: "Draft",
  },
  {
    id: 15,
    title: 'Agile Sprint',
    code: 'AGL015',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '11 Sep 2024',
    progress: '0%',
    totalEpic: 19,
    type: "Issue",
    status: "Draft",
  },
  {
    id: 16,
    title: 'Agile Scrum',
    code: 'AGL016',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '12 Sep 2024',
    progress: '0%',
    totalEpic: 20,
    type: "Issue",
    status: "Draft",
  },
]);

const columnsEpic = ref([
  { name: 'id', align: 'left', label: 'No', field: 'id' },
  { name: 'title', align: 'left', label: 'Title', field: 'title' },
  { name: 'code', align: 'left', label: 'Code', field: 'code' },
  { name: 'roadmaps', align: 'left', label: 'Roadmaps', field: 'roadmaps' },
  { name: 'type', align: 'left', label: 'Type', field: 'type' },
  { name: 'dueDate', align: 'left', label: 'Due Date', field: 'dueDate' },
  { name: 'stakeholders', align: 'left', label: 'Stakeholder', field: 'stakeholders' },
  { name: 'progress', align: 'left', label: 'Progress', field: 'progress' },
  { name: 'status', align: 'left', label: 'Status', field: 'status' },
]);
</script>

<style scoped>
.hide-scrollbar {
  scrollbar-width: none;
  /* Firefox */
  -ms-overflow-style: none;
  /* Internet Explorer 10+ */
}

.hide-scrollbar::-webkit-scrollbar {
  display: none;
  /* Safari and Chrome */
}

.text-subtitle1 {
  font-size: 14px;
  color: #333;

}

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

.q-avatar-group img {
  border: 2px solid white;
}

.title-container {
  display: flex;
  align-items: center;
  /* Align items vertically centered */
}

.icon {
  margin-right: 8px;
  /* Add space between the icon and the text */
}

.title-page {
  font-size: 12px;
  /* Adjust the font size as needed */
  font-weight: bold;
  /* Optionally make the text bold */
}

.header-container {
  display: flex;
  align-items: center;
  /* Align items vertically centered */
  gap: 8px;
  /* Adjust the gap between text and buttons */
}

.text-h6 {
  font-size: 17px;
}

.button-group {
  display: flex;
  gap: 1px;
  /* Adjust gap to control space between buttons */
}

.button {
  min-width: 10px;
  /* Adjust width if needed to ensure proper icon sizing */
  height: 10px;
  /* Adjust height to match the icon size */
}

.text-subtitle2 {
  font-size: 12px;
  margin-top: -6px;
}

.date-title {
  font-size: 13px;
  margin-left: 5px;
}

.icon-group {
  margin-left: 10px;
  /* adjust the value to your liking */
}

.long-text {
  font-size: 11px;
  margin-bottom: 0px;
}

.activeButton {
  border-bottom: 1px solid #cd202e;
  color: #cd202e;
}

.grey-column {
  background-color: #f0f0f0;
}
</style>
