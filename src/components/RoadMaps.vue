<template>
  <!-- Roadmaps -->
  <!-- <div v-if="isRoadmapsActive"> -->
  <div class="row d-flex flex-row justify-between items-center" style="gap: 5px;">
    <div class="col-2 q-ml-sm q-my-sm ">
      <q-btn flat icon="search" label="Search Roadmaps" :style="{
        'text-transform': 'none',
        'font-size': '14px',
        'border-radius': '12px',
        border: '1px solid #CED3D7',
        color: '#585858',
        width: '200px',
      }" />
    </div>
    <div class="col-5 q-my-md q-mr-lg text-right">
      <q-btn icon="auto_fix_high" class="text-subtitle2 text-capitalize" color="red-9" label="Add Roadmaps"
        @click="showModal = true" />
      <q-dialog v-model="showModal" persistent>
        <q-card style="min-width: 805px; height: 810px;">
          <q-card-section>
            <div class="header-dialog">
              <div class="text-h6">Add Roadmaps</div>
              <q-btn flat icon="close" v-close-popup />
            </div>
          </q-card-section>

          <q-separator />

          <q-card-section>
            <!-- Title Input -->
            <div class="jarak">
              <span>Title</span>
              <q-input outlined v-model="text" color="grey" label="Insert Roadmaps Title. Max 100 characters" />

              <!-- Description Input -->
              <span>Description</span>
              <q-input outlined v-model="text" color="grey" label="Insert Roadmaps Description" />

              <!-- Stakeholder Input -->
              <span>Stakeholder</span>
              <q-input outlined v-model="text" color="grey" label="Insert Name or Badge Stakeholder" />

              <!-- Content Editor -->
              <span>Content</span>
              <q-editor v-model="form.content" label="Content" filled :toolbar="[
                ['bold', 'italic', 'underline', 'strike', 'link', 'unordered', 'ordered', 'fullscreen'],
              ]" />

              <!-- Status Selection -->
              <span>Status</span>
              <!-- Status Radio Buttons -->
              <div class="q-mb-md">
                <q-option-group v-model="form.status" inline :options="statusOptions" @input="onStatusChange"
                  color="primary" />
              </div>

              <!-- Conditionally Displayed Date Pickers -->
              <div v-if="form.status === 'Release'" class="row q-gutter-md">
                <div class="col">
                  <span>Release Date</span>
                  <q-input outlined v-model="form.releaseDate">
                    <template v-slot:append>
                      <q-icon name="event" class="cursor-pointer">
                        <q-popup-proxy cover transition-show="scale" transition-hide="scale">
                          <q-date v-model="form.releaseDate" minimal mask="DD MMMM YYYY" hide-header />
                        </q-popup-proxy>
                      </q-icon>
                    </template>
                  </q-input>
                </div>
                <div class="col">
                  <span>Due Date</span>
                  <q-input outlined v-model="form.dueDate">
                    <template v-slot:append>
                      <q-icon name="event" class="cursor-pointer">
                        <q-popup-proxy cover transition-show="scale" transition-hide="scale">
                          <q-date v-model="form.dueDate" minimal mask="DD MMMM YYYY" hide-header />
                        </q-popup-proxy>
                      </q-icon>
                    </template>
                  </q-input>
                </div>
              </div>

              <!-- Conditionally Displayed Date Pickers -->
              <div v-if="form.status === 'Completed'" class="row q-gutter-md">
                <div class="col">
                  <span>Completed Date</span>
                  <q-input outlined v-model="form.releaseDate">
                    <template v-slot:append>
                      <q-icon name="event" class="cursor-pointer">
                        <q-popup-proxy cover transition-show="scale" transition-hide="scale">
                          <q-date v-model="form.releaseDate" minimal mask="DD MMMM YYYY" hide-header />
                        </q-popup-proxy>
                      </q-icon>
                    </template>
                  </q-input>
                </div>
              </div>
            </div>

          </q-card-section>
          <div class="column">
            <div class="col self-end q-mr-md">
              <q-card-actions>
                <q-btn flat label="Cancel" color="red" v-close-popup />
                <q-btn label="Submit" color="red" @click="submitForm" />
              </q-card-actions>
            </div>
          </div>
        </q-card>
      </q-dialog>
    </div>
  </div>
  <div class="table-pagination-container">
    <q-table :rows="rows" :columns="columns" flat table-style="table-layout: auto;" :pagination="initialPagination"
      hide-bottom>
      <template v-slot:header="props">
        <q-tr :props="props">
          <q-th v-for="col in props.cols" :key="col.name" :props="props"
            :class="['grey-column', { 'grey-column': col.field === 'no' || col.field === 'title' || col.field === 'dueDate' }]">
            <!-- Add icon conditionally to specific columns like 'title', 'code', 'dueDate' -->
            <q-icon size="xs" v-if="col.field === 'no'" name="expand_all" />
            <q-icon size="sm" v-if="col.field === 'title'" name="sticky_note_2" />
            <q-icon size="sm" v-if="col.field === 'code'" name="tag" />
            <q-icon size="sm" v-if="col.field === 'type'" name="sticky_note_2" />
            <q-icon size="sm" v-if="col.field === 'dueDate'" name="calendar_month" />
            <q-icon size="sm" v-if="col.field === 'stakeholders'" name="group" />
            <q-icon size="sm" v-if="col.field === 'progress'" name="percent" />
            <q-icon size="sm" v-if="col.field === 'totalEpic'" name="expand_circle_down" />

            {{ col.label }}
          </q-th>
        </q-tr>
      </template>
      <template v-slot:body-cell="props">
        <q-td :props="props">
          <div v-if="props.col.field === 'totalEpic'" class="q-mt-xs flex items-center">
            <span>{{ props.row.totalEpic }}</span>
            <q-icon name="more_vert" class="q-ml-xl cursor-pointer absolute" @click="onIconClick(props.row)" />
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
                    <q-icon name="edit" />
                  </q-item-section>
                  <q-item-section>Edit</q-item-section>
                </q-item>
                <q-item clickable v-close-popup>
                  <q-item-section side>
                    <q-icon name="delete" />
                  </q-item-section>
                  <q-item-section>Delete</q-item-section>
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
  <!-- </div> -->
</template>

<script setup>
import { ref ,reactive } from 'vue'
// export default {
//   name: 'RoadMaps'
// }

const showModal = ref(false)

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

const form = reactive({
  title: '',
  description: '',
  stakeholder: '',
  content: '',
  status: 'Draft',
  releaseDate: '',
  dueDate: ''
});

const statusOptions = [
  { label: 'Draft', value: 'Draft' },
  { label: 'Release', value: 'Release' },
  { label: 'Completed', value: 'Completed' }
];

const onStatusChange = (value) => {
  if (value !== 'Release') {
    // Reset the dates when the status is not "Release"
    form.releaseDate = '';
    form.dueDate = '';
  }
};

</script>

<style>
.jarak {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.header-dialog {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
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
</style>
