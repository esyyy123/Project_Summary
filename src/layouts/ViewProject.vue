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
          <div class="col-4">
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
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos
                        corrupti
                        commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
                        eveniet doloribus ullam aliquid.
                      </q-card-section>
                    </q-card>
                  </q-expansion-item>

                  <q-separator />

                  <q-expansion-item switch-toggle-side expand-separator label="Project Related(10)" icon="add_box">
                    <q-card>
                      <q-card-section>
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos
                        corrupti
                        commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
                        eveniet doloribus ullam aliquid.
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
                <q-list bordered>
                  <q-item v-for="stakeholder in stakeholders" :key="stakeholder.id">
                    <q-item-section avatar>
                      <q-avatar icon="person" />
                    </q-item-section>
                    <q-item-section>
                      <q-item-label>{{ stakeholder.name }}</q-item-label>
                      <q-item-label caption>{{ stakeholder.role }}</q-item-label>
                    </q-item-section>
                  </q-item>
                </q-list>
              </q-card-section>
            </q-card>
          </div>

          <!-- Right Panel - Roadmap Table -->
          <div class="col-8">
            <q-card class="q-ml-md">
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
                      <q-badge v-else-if="props.col.field === 'type'" :color="typeColor(props.row.type)" align="center">
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

const stakeholders = ref([
  { id: 1, name: 'Nurmantias (200431)', role: 'Project Manager' },
  { id: 2, name: 'Jassy Lee (200314)', role: 'Project Control' },
  { id: 3, name: 'Jemmy Ng (200341)', role: 'Project Owner' },
  // Add more stakeholders as needed
]);

const isRoadmapsActive = ref(true);
const isEpicActive = ref(false);
const isBoardActive = ref(true);
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

const rows = ref([
  {
    id: 1,
    title: 'Job Order',
    code: 'AGL001',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '28 Aug 2024',
    progress: 100,
    totalEpic: 15,
  },
  {
    id: 2,
    title: 'Master Data Part Number',
    code: 'AGL002',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '29 Aug 2024',
    progress: 100,
    totalEpic: 10,
  },
  {
    id: 3,
    title: 'Process Model',
    code: 'AGL003',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '30 Aug 2024',
    progress: 100,
    totalEpic: 20,
  },
  {
    id: 4,
    title: 'Firewall Canban List',
    code: 'AGL004',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '31 Aug 2024',
    progress: 90,
    totalEpic: 10,
  },
  {
    id: 5,
    title: 'Firewall Request Report',
    code: 'AGL005',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '1 Sep 2024',
    progress: 70,
    totalEpic: 13,
  },
  {
    id: 6,
    title: 'Detail Firewall Request',
    code: 'AGL006',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '2 Sep 2024',
    progress: 50,
    totalEpic: 6,
  },
  {
    id: 7,
    title: 'Handover PLC Communication for Battery Cover Inspection',
    code: 'AGL007',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '3 Sep 2024',
    progress: 30,
    totalEpic: 15,
  },
  {
    id: 8,
    title: 'RPA for Simplified HR in HRMS and Government Portal',
    code: 'AGL008',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '4 Sep 2024',
    progress: 0,
    totalEpic: 13,
  },
  {
    id: 9,
    title: 'Controller',
    code: 'AGL006',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    dueDate: '2 Sep 2024',
    progress: 50,
    totalEpic: 6,
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
  rowsPerPage: 10
  // rowsNumber: xx if getting data from a server
}
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
  font-size: 19px;
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
</style>
