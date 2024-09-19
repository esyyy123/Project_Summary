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
              <!-- header -->
              <q-card-section>
                <div class="header-container">
                  <div class="text-h6">
                    AGL001 - Project Management Agile Board 2.0
                    <span class="icon-group">
                      <q-icon name="delete" title="Delete" size="20px" />
                      <q-icon name="edit" title="Edit" size="20px" @click="showEdit = true" />
                      <q-dialog v-model="showEdit" persistent>
                        <q-card style="min-width: 805px; height: 580px;">
                          <q-card-section>
                            <div class="header-dialog">
                              <div class="text-h6">Edit Project</div>
                              <q-btn flat icon="close" v-close-popup />
                            </div>
                          </q-card-section>

                          <q-separator />

                          <q-card-section>
                            <!-- Title Input -->
                            <div class="jarak">
                              <span>Title</span>
                              <q-input outlined v-model="text" color="grey"
                                label="Project Management Agile Board 2.0" />

                              <div class="q-mt-md">
                                <span>Content</span>
                                <q-editor v-model="form.content" filled :toolbar="[
                                  ['bold', 'italic', 'underline', 'strike'],
                                  ['link', 'unordered', 'ordered', 'fullscreen']
                                ]" />
                              </div>

                              <span>Departement Owner</span>
                              <q-select outlined v-model="form.owner" :options="OwnerOptions" />
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
              <!-- <q-list bordered /> -->
              <q-separator />
              <!-- body -->
              <div class="wrapper"></div>
              <div class="q-pa-md" style="max-width: 512px">
                <q-list bordered class="rounded-borders">
                  <q-expansion-item switch-toggle-side expand-separator label="Information">
                    <q-separator />
                    <q-card>
                      <q-card-section>
                        <!-- Project Type -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle2">Project Type</span>
                          </q-item-section>
                          <q-item-section>
                            <span class="text2">IT</span>
                          </q-item-section>
                        </q-item>

                        <!-- Project Description -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle2">Project Description</span>
                          </q-item-section>
                          <q-item-section>
                            <span class="text2">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
                              tempor
                              incididunt ut labore et dolore magna aliqua.</span>
                          </q-item-section>
                        </q-item>

                        <!-- Department -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle2">Department</span>
                          </q-item-section>
                          <q-item-section>
                            <span class="text2">DOT</span>
                          </q-item-section>
                        </q-item>

                        <!-- Department Owner -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle2">Department Owner</span>
                          </q-item-section>
                          <q-item-section>
                            <span class="text2">DOT</span>
                          </q-item-section>
                        </q-item>

                        <!-- Project Manager -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle2">Project Manager</span>
                          </q-item-section>
                          <q-item-section>
                            <div class="row items-center no-wrap">
                              <q-avatar size="md" class="q-mr-sm">
                                <img src="src/assets/auraa.png" alt="avatar">
                              </q-avatar>
                              <span class="text2">Nurmatias (123456)</span>
                            </div>
                          </q-item-section>
                        </q-item>

                        <!-- Release Date -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle2">Release</span>
                          </q-item-section>
                          <q-item-section>
                            <span class="text2">26 Aug 2024 - 30 Aug 2024</span>
                          </q-item-section>
                        </q-item>

                        <!-- Status -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle2">Status</span>
                          </q-item-section>
                          <q-item-section>
                            <q-badge label="Completed" color="green-11" text-color="black" style="width: 72px;" />
                          </q-item-section>
                        </q-item>

                        <!-- Progress -->
                        <q-item>
                          <q-item-section>
                            <span class="text-subtitle2">Progress</span>
                          </q-item-section>
                          <q-item-section>
                            <q-badge label="100%" color="amber-2" text-color="black" style="width: 40px;" />
                          </q-item-section>
                        </q-item>
                      </q-card-section>
                    </q-card>
                  </q-expansion-item>

                  <q-separator />

                  <q-expansion-item switch-toggle-side expand-separator label="Project Related(10)">
                    <template v-slot:header>
                      <div class="row items-center">
                        <div>Project Related(10)</div>
                        <q-icon size="20px" name="add_box" class="q-ml-sm" @click="showProject = true" />
                        <q-dialog v-model="showProject" persistent>
                          <q-card style="min-width: 500px; height: 250px;">
                            <q-card-section>
                              <div class="header-dialog">
                                <div class="text-h6">Add Project Related</div>
                                <q-btn flat icon="close" v-close-popup />
                              </div>
                            </q-card-section>

                            <q-separator />

                            <q-card-section>
                              <!-- Title Input -->
                              <div class="jarak">

                                <span>Select Project</span>
                                <q-select outlined v-model="form.project" :options="ProjectOptions" />
                              </div>
                            </q-card-section>
                            <div class="column">
                              <div class="col self-end q-mr-md">
                                <q-card-actions>
                                  <q-btn flat label="Cancel" color="red" v-close-popup />
                                  <q-btn label="Add" color="red" @click="submitForm" />
                                </q-card-actions>
                              </div>
                            </div>
                          </q-card>
                        </q-dialog>
                      </div>
                    </template>
                    <q-separator />
                    <q-card>
                      <q-card-section>
                        <div class="table-pagination-container">
                          <q-table :rows="rowsProject" :columns="columnsProject" flat table-style="table-layout: auto;"
                            :pagination="initialPagination" hide-bottom class="small-table" style="font-size: 5px;">
                            <template v-slot:header="props">
                              <q-tr :props="props">
                                <q-th v-for="col in props.cols" :key="col.name" :props="props"
                                  :class="['grey-column', { 'grey-column': col.field === 'no' || col.field === 'projectTitle' }]"
                                  style="padding: 2px; font-size: 11px;">
                                  <!-- Add icon conditionally to specific columns like 'title', 'code', 'dueDate' -->
                                  <q-icon size="xs" v-if="col.field === 'project title'" name="person" />
                                  <q-icon size="xs" v-if="col.field === 'PM'" name="personal_injury" />
                                  <q-icon size="xs" v-if="col.field === 'Progress'" name="personal_injury" />
                                  {{ col.label }}
                                </q-th>
                              </q-tr>
                            </template>
                            <template v-slot:body-cell="props">
                              <q-td :props="props">
                                <div v-if="props.col.field === 'progress'"
                                  class="q-mt-xs flex items-center justify-between">
                                  <span>{{ props.row.progress }}</span>
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
                    <q-icon name="add_box" size="19px" @click="showStekh = true" />
                    <q-dialog v-model="showStekh" persistent>
                      <q-card style="min-width: 700px; height: 400px;">
                        <q-card-section>
                          <div class="header-dialog">
                            <div class="text-h6">Add Stakeholder</div>
                            <q-btn flat icon="close" v-close-popup />
                          </div>
                        </q-card-section>

                        <q-separator />

                        <q-card-section>
                          <!-- Title Input -->
                          <div class="jarak">

                            <span>Nama</span>
                            <q-select outlined v-model="form.project" :options="StekhOptions" />

                            <span>Role</span>
                            <q-option-group v-model="group" :options="options" color="primary" inline />

                            <span>Role Alias</span>
                            <q-input outlined v-model="text" color="grey" label="Insert Role Alias  " />
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
                    <q-btn icon="auto_fix_high" class="text-subtitle2 text-capitalize" color="red-9"
                      label="Add Roadmaps" @click="showModal = true" />
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
                            <q-input outlined v-model="text" color="grey"
                              label="Insert Roadmaps Title. Max 100 characters" />

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
                              <q-option-group v-model="form.status" inline :options="statusOptions"
                                @input="onStatusChange" color="primary" />
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
                  <q-table :rows="rows" :columns="columns" flat table-style="table-layout: auto;"
                    :pagination="initialPagination" hide-bottom>
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
                  <div class="col-5 q-ml-sm q-my-sm">
                    <div class="row q-gutter-x-sm">
                      <q-btn flat icon="search" label="Search Requirement" :style="{
                        'text-transform': 'none',
                        'font-size': '14px',
                        'border-radius': '12px',
                        border: '1px solid #CED3D7',
                        color: '#585858',
                        width: '200px',
                      }" />
                      <q-btn flat icon="filter_list" label="Filter" @click="showFilter = true" :style="{
                        'text-transform': 'none',
                        'font-size': '14px',
                        'border-radius': '12px',
                        border: '1px solid #CED3D7',
                        color: '#585858',
                      }" />
                      <q-dialog v-model="showFilter" persistent>
                        <q-card style="min-width: 505px; height: 430px;">
                          <q-card-section>
                            <div class="header-dialog">
                              <div class="text-h6">Filter Epic</div>
                              <q-btn flat icon="close" v-close-popup />
                            </div>
                          </q-card-section>

                          <q-separator />

                          <q-card-section>
                            <!-- Title Input -->
                            <div class="jarak">
                              <span>Type</span>
                              <q-select outlined v-model="form.filter" :options="TipeOptions" label="All Type" />

                              <span>Roadmaps</span>
                              <q-select outlined v-model="form.road" :options="roadOptions" label="All Roadmaps" />

                              <span>Status</span>
                              <q-select outlined v-model="form.statuss" :options="StatsOptions" label="All Status" />
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
                  <div class="col-5 q-my-md q-mr-lg text-right">
                    <q-btn icon="auto_fix_high" class="text-subtitle2 text-capitalize" color="red-9" label="Add Epic"
                      @click="dialogVisible = true" />
                    <q-dialog v-model="dialogVisible" persistent>
                      <q-card style="min-width: 805px; height: 810px;">
                        <q-card-section class="row items-center justify-between">
                          <span class="text-h6">Add Epic</span>
                          <q-btn flat dense icon="close" @click="dialogVisible = false" />
                        </q-card-section>

                        <q-card-section>
                          <!-- Title Input -->
                          <span>Title</span>
                          <q-input outlined v-model="form.title" color="grey"
                            label="Insert Requirement Title. Max 100 characters" />

                          <!-- Type Radio Buttons -->
                          <div class="q-mt-md">
                            <span>Type</span>
                            <q-option-group inline v-model="form.type" :options="TypeOptions" @input="onTypeChange"
                              color="primary" />
                          </div>
                          <!-- Conditionally Displayed Date Pickers -->
                          <div v-if="form.type === 'Change Request'" class="row q-gutter-md">
                            <div class="col">
                              <span>Requirement</span>
                              <q-input outlined v-model="form.requirement" color="grey"
                                label="Insert Requirement Title. Max 100 characters" />
                            </div>
                          </div>
                          <!-- Conditionally Displayed Date Pickers -->
                          <div v-if="form.type === 'Issue'" class="row q-gutter-md">
                            <div class="col">
                              <span>Issue</span>
                              <q-select outlined v-model="form.issue" :options="issueOptions" label="Choose issue" />
                            </div>
                          </div>


                          <!-- Roadmaps Dropdown -->
                          <div class="q-mt-md">
                            <span>Roadmaps</span>
                            <q-select outlined v-model="form.roadmap" :options="roadmapsOptions"
                              label="Choose Roadmaps" />
                          </div>


                          <!-- Description Editor -->
                          <div class="q-mt-md">
                            <span>Description</span>
                            <q-editor v-model="form.description" label="Insert Content of Requirement" filled :toolbar="[
                              ['bold', 'italic', 'underline', 'strike'],
                              ['link', 'unordered', 'ordered', 'fullscreen']
                            ]" />
                          </div>

                          <!-- Status Selection -->
                          <span>Status</span>
                          <!-- Status Radio Buttons -->
                          <div class="q-mb-md">
                            <q-option-group v-model="form.status" inline :options="statusOptions"
                              @input="onStatusChange" color="primary" />
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

                          <div class="column">
                            <div class="col self-end q-mr-sm">
                              <q-card-actions>
                                <q-btn flat label="Cancel" color="red" v-close-popup />
                                <q-btn label="Submit" color="red" @click="submitForm" />
                              </q-card-actions>
                            </div>
                          </div>
                        </q-card-section>
                      </q-card>
                    </q-dialog>
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
                          <q-icon size="sm" v-if="col.field === 'title'" name="sticky_note_2" />
                          <q-icon size="sm" v-if="col.field === 'code'" name="tag" />
                          <q-icon size="sm" v-if="col.field === 'roadmaps'" name="route" />
                          <q-icon size="sm" v-if="col.field === 'type'" name="sticky_note_2" />
                          <q-icon size="sm" v-if="col.field === 'dueDate'" name="calendar_month" />
                          <q-icon size="sm" v-if="col.field === 'stakeholders'" name="group" />
                          <q-icon size="sm" v-if="col.field === 'progress'" name="percent" />
                          <q-icon size="sm" v-if="col.field === 'status'" name="expand_circle_down" />

                          {{ col.label }}
                        </q-th>
                      </q-tr>
                    </template>
                    <template v-slot:body-cell="props">
                      <q-td :props="props">
                        <div v-if="props.col.field === 'Status'" class="q-mt-xs flex items-center justify-between">
                          <span>{{ props.row.status }}</span>
                          <q-icon name="more_vert" class="q-ml-xxl cursor-pointer absolute"
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
                          <div class="avatar" style="background-image: url('src/assets/auraa.png');"></div>
                        </div>
                        <q-badge v-else-if="props.col.field === 'type'" :color="typeColor(props.row.type)"
                          align="center">
                          {{ props.row.type }}
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
                <div class="row d-flex flex-row justify-between items-center" style="gap: 5px;">
                  <div class="col-5 q-ml-sm q-my-sm">
                    <div class="row q-gutter-x-sm">
                      <q-btn flat icon="chevron_right" label="Expand All" :style="{
                        'text-transform': 'none',
                        'font-size': '15px',
                        'border-radius': '12px',
                        border: '1px solid #CED3D7',
                        color: '#585858',
                      }" />
                      <q-btn flat icon="keyboard_control_key" label="Colapse All" :style="{
                        'text-transform': 'none',
                        'font-size': '15px',
                        'border-radius': '12px',
                        border: '1px solid #CED3D7',
                        color: '#585858',
                      }" />
                    </div>

                  </div>
                  <div class="col-5 q-my-md q-mr-lg text-right">
                    <q-btn icon="autorenew" class="text-subtitle2 text-capitalize q-mr-md" label="Auto Generate"
                      style="background-color: white; border: 2px solid red; color: red; border-radius: 10px;"
                      @click="showAuto = true" />
                    <q-btn icon="auto_fix_high" class="text-subtitle2 text-capitalize" color="red-9" label="Add Board"
                      @click="showBoard = true" />
                    <q-dialog v-model="showBoard" persistent>
                      <q-card style="min-width: 805px; height: 450px;">
                        <q-card-section>
                          <div class="header-dialog">
                            <div class="text-h6">Add Board</div>
                            <q-btn flat icon="close" v-close-popup />
                          </div>
                        </q-card-section>

                        <q-separator />

                        <q-card-section>
                          <!-- Title Input -->
                          <div class="jarak">
                            <span>Title</span>
                            <q-input outlined v-model="text" color="grey" label="Insert Board Title" />

                            <span>Sequence</span>
                            <q-input v-model="numberValue" type="number" outlined :min="0" :max="100" :step="1" />

                            <span>Board Privileges</span>
                            <q-input outlined v-model="text" color="grey" label="Insert Name or Badge Privileges" />
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

                <div id="q-app" style="min-height: 100vh;">
                  <div class="q-pa-none">
                    <q-table flat bordered :rows="rowsBoard" :columns="columnsBoard" row-key="name" hide-bottom
                      auto-width>
                      <template v-slot:header="props">
                        <q-tr :props="props" class="grey-column">
                          <q-th auto-width></q-th>
                          <q-th v-for="col in props.cols" :key="col.name" :props="props">
                            {{ col.label }}
                          </q-th>
                        </q-tr>
                      </template>

                      <template v-slot:body="props">
                        <q-tr :props="props">
                          <q-td auto-width>
                            <q-btn size="sm" round dense @click="props.expand = !props.expand"
                              :icon="props.expand ? 'remove' : 'chevron_right'"></q-btn>
                          </q-td>
                          <q-td class="text-left" v-for="col in props.cols" :key="col.name" :props="props">
                            <template v-if="col.field === 'pic'">
                              <q-td class="text-right">
                                <div class="avatar" style="background-image: url('src/assets/auraa.png');"></div>
                              </q-td>
                            </template>
                            {{ col.value }}
                          </q-td>
                        </q-tr>

                        <q-tr v-show="props.expand" :props="props"
                          v-for="(row, index) in getExpandedData(props.row.name)" :key="index">
                          <q-td colspan="100%">
                            <div class="row" style="margin-left:60px;">
                              <div class="col">{{ row.id }}</div>
                              <div class="col text-left">{{ row.status }}</div>
                              <div class="col text-center">{{ row.number1 }}</div>
                              <div class="col text-right">{{ row.number2 }}</div>
                              <div class="col row justify-end">
                                <div :class="row.bgColor"
                                  style="width: 25px; height: 20px; border-radius: 5px; justify-content: end"></div>
                              </div>
                              <div class="col text-right">
                                <img src="src/assets/silang.svg" style="width: 20px; height: 20px;" />
                              </div>
                              <div class="col text-right">
                                <img src="src/assets/centang.svg" style="width: 20px; height: 20px;" />
                              </div>
                            </div>
                          </q-td>
                        </q-tr>
                      </template>
                    </q-table>
                  </div>
                </div>
              </div>

              <!-- Documentation -->
              <div v-if="isDocumActive">
                <div class="col-2 q-ml-sm q-my-sm">
                  <q-btn flat icon="chevron_right" label="Expand All" :style="{
                    'text-transform': 'none',
                    'font-size': '15px',
                    'border-radius': '12px',
                    border: '1px solid #CED3D7',
                    color: '#585858',
                  }" />
                  <q-btn flat icon="keyboard_control_key" label="Colapse All" :style="{
                    'text-transform': 'none',
                    'font-size': '15px',
                    'border-radius': '12px',
                    border: '1px solid #CED3D7',
                    color: '#585858',
                  }" />
                </div>
                <div class="statuses-indicators" :style="{
                  'text-transform': 'none',
                  'font-size': '16px',
                  color: '#585858',
                }">
                  <div v-for="statuses in statuses" :key="statuses.label">
                    <q-badge :style="{ width: '16px', height: '16px' }" class="no-background">
                      <img :src="statuses.src" alt="icon" style="width: 16px; height: 16px;" />
                    </q-badge>
                    <span class="q-ml-sm">{{ statuses.label }}</span>
                  </div>
                </div>
                <div class="col-5 q-my-md q-mr-lg text-right">
                  <q-btn icon="edit" class="text-subtitle2 text-capitalize" color="red-9" label="Add Group"
                    @click="showModal = true" />
                  <q-dialog v-model="showModal" persistent>
                    <q-card style="min-width: 805px; height: 500px;">
                      <q-card-section>
                        <div class="header-dialog">
                          <div class="text-h6">Add Group</div>
                          <q-btn flat icon="close" v-close-popup />
                        </div>
                      </q-card-section>

                      <q-separator />

                      <q-card-section>
                        <!-- Title Input -->
                        <div class="jarak">
                          <span>Title</span>
                          <q-input outlined v-model="text" color="grey"
                            label="Insert Group Title. Max 100 characters" />

                          <div class="q-mt-md">
                            <span>Description</span>
                            <q-editor v-model="form.description" label="Insert Content of Requirement" filled :toolbar="[
                              ['bold', 'italic', 'underline', 'strike'],
                              ['link', 'unordered', 'ordered', 'fullscreen']
                            ]" />
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
                <div class="q-pa-md q-gutter-sm">
                  <div id="q-app" style="min-height: 100vh;">
                    <q-tree :nodes="treeData" node-key="id" :filter-method="filterMethod" no-tick>
                      <template v-slot:default-header="props">
                        <q-item v-ripple @click="props.node.expand = !props.node.expand">

                          <!-- Conditionally show Add box icon for specific labels -->
                          <q-item-section side
                            v-if="['Login', 'Module Login', 'Project', 'Project Summary', 'Module Project Summary'].includes(props.node.label)">
                            <q-btn flat dense icon="add_box" @click="showAdd = true" />
                            <q-dialog v-model="showAdd" persistent>
                              <q-card style="min-width: 800px; height: 715px;">
                                <q-card-section>
                                  <div class="header-dialog">
                                    <div class="text-h6">Add Group or Module</div>
                                    <q-btn flat icon="close" v-close-popup />
                                  </div>
                                </q-card-section>

                                <q-separator />

                                <q-card-section>
                                  <!-- Title Input -->
                                  <div class="jarak">

                                    <div class="q-mt-md">
                                      <span>Type</span>
                                      <q-option-group inline v-model="form.tipe" :options="TipeeOptions"
                                        @input="onTipeeChange" color="primary" />
                                    </div>


                                    <span>Title</span>
                                    <q-input outlined v-model="text" color="grey"
                                      label="Insert Title.Max 100 characters  " />

                                    <!-- Conditionally Displayed Date Pickers -->
                                    <div v-if="form.tipe === 'Module'" class="row q-gutter-md">
                                      <div class="col">
                                        <span>Relation Module</span>
                                        <q-select outlined v-model="form.module" :options="moduleOptions" />
                                      </div>
                                    </div>

                                    <span>Description</span>
                                    <q-editor v-model="form.content" label="Content" filled :toolbar="[
                                      ['bold', 'italic', 'underline', 'strike', 'link', 'unordered', 'ordered', 'fullscreen'],
                                    ]" />

                                    <div v-if="form.tipe === 'Module'" class="row q-gutter-md">
                                      <div class="col">
                                        <span>Multiple Image (Optional)</span>
                                        <q-input outlined color="grey" @update:model-value="val => { file = val[0] }"
                                          type="file" />
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
                          </q-item-section>
                          <q-item-section>
                            <q-item-label>{{ props.node.label }}</q-item-label>
                          </q-item-section>
                          <q-item style="display: flex; justify-content: flex-end;">
                            <q-item-section side>
                              <q-chip :color="props.node.statusColor" :outline="true" square >
                                {{ props.node.status }} ({{ props.node.progress }})
                              </q-chip>
                            </q-item-section>
                          </q-item>
                        </q-item>
                      </template>
                    </q-tree>
                  </div>
                </div>
              </div>

              <!-- Activities -->
              <div v-if="isActivitiesActive">
                <div class="row d-flex flex-row justify-between items-center" style="gap: 5px;">
                  <div class="col-5 q-ml-sm q-my-sm">
                    <div class="row q-gutter-x-sm">
                      <q-btn flat icon="search" label="Search Requirement" :style="{
                        'text-transform': 'none',
                        'font-size': '14px',
                        'border-radius': '12px',
                        border: '1px solid #CED3D7',
                        color: '#585858',
                        width: '200px',
                      }" />
                      <q-btn flat icon="filter_list" label="Filter" @click="showFilter = true" :style="{
                        'text-transform': 'none',
                        'font-size': '14px',
                        'border-radius': '12px',
                        border: '1px solid #CED3D7',
                        color: '#585858',
                      }" />
                      <q-dialog v-model="showFilter" persistent>
                        <q-card style="min-width: 505px; height: 430px;">
                          <q-card-section>
                            <div class="header-dialog">
                              <div class="text-h6">Filter Epic</div>
                              <q-btn flat icon="close" v-close-popup />
                            </div>
                          </q-card-section>

                          <q-separator />

                          <q-card-section>
                            <!-- Title Input -->
                            <div class="jarak">
                              <span>Type</span>
                              <q-select outlined v-model="form.filter" :options="TipeOptions" label="All Type" />

                              <span>Roadmaps</span>
                              <q-select outlined v-model="form.road" :options="roadOptions" label="All Roadmaps" />

                              <span>Status</span>
                              <q-select outlined v-model="form.statuss" :options="StatsOptions" label="All Status" />
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
                  <div class="col-5 q-my-md q-mr-lg text-right">
                    <q-btn icon="auto_fix_high" class="text-subtitle2 text-capitalize" color="red-9"
                      label="Add Activities" @click="showAct = true" />
                    <q-dialog v-model="showAct" persistent>
                      <q-card style="min-width: 1300px; height: 850px;">
                        <!-- Dialog Header -->
                        <q-card-section>
                          <div class="header-dialog">
                            <div class="text-h6">Filter Activity</div>
                            <q-btn flat icon="close" v-close-popup />
                          </div>
                        </q-card-section>

                        <!-- Form Content -->
                        <q-separator />

                        <q-card-section>
                          <q-form>
                            <div class="row q-col-gutter-md">
                              <!-- Left section: Title, Description, and Content -->
                              <div class="col-8">
                                <div class="q-ma-sm q-mt-lg">
                                  <span>Title</span>
                                  <q-input outlined v-model="text" color="grey" label="Input Title  " />
                                </div>

                                <div class="q-ma-sm q-mt-lg">
                                  <span>Description</span>
                                  <q-input outlined v-model="text" color="grey" label="Input Description  " />
                                </div>

                                <div class="q-ma-sm q-mt-lg">
                                  <span>Content</span>
                                  <q-editor style="height: 382px;" v-model="form.content" label="Content" filled
                                    :toolbar="[
                                      ['bold', 'italic', 'underline', 'strike', 'link', 'unordered', 'ordered', 'fullscreen'],
                                    ]" />
                                </div>
                              </div>

                              <!-- Right section: Form options -->
                              <div class="col-4">
                                <q-card-section class="ACTIV">
                                  <div class="q-ma-sm q-mt-md">
                                    <span>Activity</span>
                                    <q-select outlined color="grey" v-model="activityType" :options="activityOptions"
                                      class="bg-white" />
                                  </div>

                                  <div class="q-ma-sm q-mt-lg">
                                    <span>Start Date</span>
                                    <q-input outlined color="grey" v-model="startDate" label="Start Date"
                                      class="bg-white">
                                      <template v-slot:append>
                                        <q-icon name="event" />
                                      </template>
                                    </q-input>
                                  </div>

                                  <div class="q-ma-sm q-mt-lg">
                                    <span>End Date</span>
                                    <q-input outlined color="grey" v-model="endDate" label="End Date" class="bg-white">
                                      <template v-slot:append>
                                        <q-icon name="event" />
                                      </template>
                                    </q-input>
                                  </div>

                                  <div class="q-ma-sm q-mt-lg">
                                    <span>Status</span>
                                    <q-select outlined color="grey" v-model="status" label="Status"
                                      :options="statusOptions" class="bg-white" />
                                  </div>

                                  <div class="q-ma-sm q-mt-lg">
                                    <span>Assignee</span>
                                    <q-input outlined color="grey" v-model="assignee" label="Assignee"
                                      class="bg-white" />


                                    <q-chip removable v-if="assignee">
                                      <q-avatar>
                                        <q-icon name="person" />
                                      </q-avatar>
                                      {{ assignee }}
                                    </q-chip>
                                  </div>

                                  <div class="q-ma-sm q-mt-lg">
                                    <span>Link To</span>
                                    <q-select outlined color="grey" v-model="linkTo" label="Link To"
                                      :options="linkOptions" class="bg-white" />
                                  </div>
                                </q-card-section>
                              </div>
                            </div>
                          </q-form>
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
                  <q-table :rows="rowsActiv" :columns="columnsActiv" flat table-style="table-layout: auto;"
                    :pagination="initialPagination" hide-bottom>
                    <template v-slot:header="props">
                      <q-tr :props="props">
                        <q-th v-for="col in props.cols" :key="col.name" :props="props"
                          :class="['grey-column', { 'grey-column': col.field === 'no' || col.field === 'title' || col.field === 'endDate' }]">
                          <!-- Add icon conditionally to specific columns like 'title', 'code', 'dueDate' -->
                          <q-icon size="lg" v-if="col.field === 'no'" name="expand_all" />
                          <q-icon size="sm" v-if="col.field === 'title'" name="sticky_note_2" />
                          <q-icon size="sm" v-if="col.field === 'code'" name="tag" />
                          <q-icon size="sm" v-if="col.field === 'description'" name="description" />
                          <q-icon size="sm" v-if="col.field === 'startDate'" name="sticky_note_2" />
                          <q-icon size="sm" v-if="col.field === 'endDate'" name="calendar_month" />
                          <q-icon size="sm" v-if="col.field === 'participant'" name="group" />
                          <q-icon size="sm" v-if="col.field === 'linkTo'" name="percent" />
                          <q-icon size="sm" v-if="col.field === 'status'" name="expand_circle_down" />

                          {{ col.label }}
                        </q-th>
                      </q-tr>
                    </template>
                    <template v-slot:body-cell="props">
                      <q-td :props="props">
                        <div v-if="props.col.field === 'Status'" class="q-mt-xs flex items-center justify-between">
                          <span>{{ props.row.status }}</span>
                          <q-icon name="more_vert" class="q-ml-xxl cursor-pointer absolute"
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
                        <div v-else-if="props.col.field === 'participant'" class="q-gutter-xs flex">
                          <div class="avatar" style="background-image: url('src/assets/auraa.png');"></div>
                        </div>
                        <q-badge v-else-if="props.col.field === 'activity'" :color="ActivityColor(props.row.activity)"
                          align="center">
                          {{ props.row.activity }}
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
            </q-card>
          </div>
        </q-page>
      </div>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import { reactive } from 'vue';

defineOptions({
  name: 'ViewProject',
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
    case 'Done':
      return 'green';
  }
};

const ActivityColor = (activity) => {
  switch (activity) {
    case 'Meeting':
      return 'orange';
    case 'Visit':
      return 'purple';
  }
};

// const StatColor = (stat) => {
//   switch (stat) {
//     case 'Done':
//       return 'green';
//     case 'On Going':
//       return 'blue';
//     case 'Draft':
//       return 'grey';
//   }
// };

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
  console.log('ini board', activateBoard)
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

const columnsProject = ref([
  { name: 'id', align: 'left', label: 'No', field: 'id' },
  { name: 'projectTitle', align: 'left', label: 'Project Title', field: 'projectTitle' },
  { name: 'PM', align: 'left', label: 'PM', field: 'PM' },
  { name: 'progress', align: 'left', label: 'Progress', field: 'progress' },
])

const rowsProject = ref([
  {
    id: 1,
    projectTitle: 'Project Management Agile',
    PM: '',
    progress: '100%',
  },
  {
    id: 2,
    projectTitle: 'Plant Maintenance 3.0',
    PM: '',
    progress: '60%',
  },
  {
    id: 3,
    projectTitle: 'Engineering Change Notice',
    PM: '',
    progress: '50%',
  },
  {
    id: 4,
    projectTitle: 'Smart Parking',
    PM: '',
    progress: '100%',
  },
  {
    id: 5,
    projectTitle: 'Meeting Room',
    PM: '',
    progress: '90%',
  },
  {
    id: 6,
    projectTitle: 'MySatnusa mobile 3.0',
    PM: '',
    progress: '70%',
  },
  {
    id: 7,
    projectTitle: 'Cora 2.0',
    PM: '',
    progress: '50%',
  },
  {
    id: 8,
    projectTitle: 'PCB Visual Inspection',
    PM: '',
    progress: '70%',
  },
  {
    id: 9,
    projectTitle: 'Xiaomi Face Recognition',
    PM: '',
    progress: '80%',
  },
  {
    id: 10,
    projectTitle: 'Inspect Batery Cover',
    PM: '',
    progress: '70%',
  },
  {
    id: 11,
    projectTitle: 'Project Management 2.0',
    PM: '',
    progress: '40%',
  },
  {
    id: 12,
    projectTitle: 'Project Management 2.0',
    PM: '',
    progress: '20%',
  },
])


const columnsSketh = ref([
  { name: 'id', align: 'left', label: 'No', field: 'id' },
  // { name: 'avatar', align: 'left', label: 'avatar', field: 'avatar' },
  { name: 'name', align: 'left', label: 'Name', field: 'name' },
  { name: 'role', align: 'left', label: 'Role', field: 'role' },
])

const rowsSketh = ref([
  {
    id: 1,
    avatar: 'src/assets/auraa.png',
    name: 'Nurmantias (200431)',
    role: 'Project Manager',
  },
  {
    id: 2,
    avatar: 'src/assets/auraa.png',
    name: 'Jassy Lee (200314)',
    role: 'Project Control',
  },
  {
    id: 3,
    avatar: 'src/assets/auraa.png',
    name: 'Jemmy Ng (200341)',
    role: 'Project Owner',
  },
  {
    id: 4,
    avatar: 'src/assets/auraa.png',
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
    title: 'PM Tools Phase 3',
    code: 'RQR011',
    roadmaps: 'Checksheet',
    type: "Issue",
    dueDate: '6 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Draft",
  },
  {
    id: 12,
    title: 'PM Tools Phase 2',
    code: 'RQR012',
    roadmaps: 'Asset Equipment Approval Web',
    type: "Issue",
    dueDate: '7 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Draft",
  },
  {
    id: 13,
    title: 'PM Tools Phase 1',
    code: 'RQR013',
    roadmaps: 'Guets Approval',
    type: "Issue",
    dueDate: '7 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Draft",
  },
  {
    id: 14,
    title: 'Plant Maintenance',
    code: 'RQR014',
    roadmaps: 'E-Kiosk 2.0',
    type: "Issue",
    dueDate: '7 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Draft",
  },
  {
    id: 15,
    title: 'Plant Maintenance 2',
    code: 'RQR015',
    roadmaps: 'Agile Sprint',
    type: "Issue",
    dueDate: '8 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Draft",
  },
  {
    id: 16,
    title: 'Plant Maintenance 3',
    code: 'RQR016',
    roadmaps: 'Agile Scrum',
    type: "Issue",
    dueDate: '17 Sep 2024',
    stakeholders: [{ id: 1, avatar: 'user1.jpg' }, { id: 2, avatar: 'user2.jpg' }],
    progress: '0%',
    status: "Draft",
  },
]);

const columnsActiv = ref([
  { name: 'id', align: 'left', label: 'No', field: 'id' },
  { name: 'title', align: 'left', label: 'Title', field: 'title' },
  { name: 'code', align: 'left', label: 'Code', field: 'code' },
  { name: 'activity', align: 'left', label: 'Activity', field: 'activity' },
  { name: 'description', align: 'left', label: 'Description', field: 'description' },
  { name: 'startDate', align: 'left', label: 'Start Date', field: 'startDate' },
  { name: 'endDate', align: 'left', label: 'End Date', field: 'endDate' },
  { name: 'participant', align: 'left', label: 'Participant', field: 'participant' },
  { name: 'linkTo', align: 'left', label: 'Link To', field: 'linkTo' },
  { name: 'status', align: 'left', label: 'Status', field: 'status' },
]);

const rowsActiv = ref([
  {
    id: 1,
    title: 'MES System SPP Departement',
    code: 'RQR001',
    activity: 'Meeting',
    description: 'Job Order',
    startDate: '27 Agu 2024,17.00',
    endDate: '28 Aug 2024,17.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Roadmaps',
    status: "Done",
  },
  {
    id: 2,
    title: 'Boards',
    code: 'RQR002',
    activity: 'Meeting',
    description: 'Master Data Part Number',
    startDate: '29 Agu 2024,17.00',
    endDate: '30 Aug 2024,17.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Roadmaps',
    status: "Done",
  },
  {
    id: 3,
    title: 'Product Monitoring',
    code: 'RQR003',
    activity: 'Meeting',
    description: 'Process Model',
    startDate: '30 Agu 2024,10.00',
    endDate: '30 Aug 2024,17.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Roadmaps',
    status: "Done",
  },
  {
    id: 4,
    title: 'RPA for Simplified Purchasing',
    code: 'RQR004',
    activity: 'Meeting',
    description: 'Firewall Canban List',
    startDate: '31 Agu 2024,11.00',
    endDate: '31 Aug 2024,17.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Roadmaps',
    status: "Done",
  },
  {
    id: 5,
    title: 'ML-Powered Interception of False',
    code: 'RQR005',
    activity: 'Meeting',
    description: 'Firewall Request Report',
    startDate: '1 Sep 2024,07.00',
    endDate: '1 Sep 2024,15.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Roadmaps',
    status: "On Going",
  },
  {
    id: 6,
    title: 'Pcb Counter using computer vision',
    code: 'RQR006',
    activity: 'Meeting',
    description: 'Detail Firewall Request',
    startDate: '2 Sep 2024,07.00',
    endDate: '2 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Epic',
    status: "On Going",
  },
  {
    id: 7,
    title: 'Handover PLC Communication',
    code: 'RQR007',
    activity: 'Meeting',
    description: 'Handover PLC Communication',
    startDate: '3 Sep 2024,07.00',
    endDate: '3 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Epic',
    status: "On Going",
  },
  {
    id: 8,
    title: 'RPA for Simplified HR in HRMS',
    code: 'RQR008',
    activity: 'Meeting',
    description: 'RPA for Simplified HR in HRMS',
    startDate: '4 Sep 2024,07.00',
    endDate: '4 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Epic',
    status: "On Going",
  },
  {
    id: 9,
    title: 'Controller dehumidifier iot (SMT)',
    code: 'RQR009',
    activity: 'Meeting',
    description: 'Controller dehumidifier iot (SMT)',
    startDate: '5 Sep 2024,07.00',
    endDate: '5 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Epic',
    status: "On Going",
  },
  {
    id: 10,
    title: 'PM Tools Phase 4 (Agile)',
    code: 'RQR010',
    activity: 'Visit',
    description: 'PM Tools Phase 4 (Agile)',
    startDate: '6 Sep 2024,07.00',
    endDate: '6 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Story',
    status: "On Going",
  },
  {
    id: 11,
    title: 'PM Tools Phase 3',
    code: 'RQR011',
    activity: 'Visit',
    description: 'Checksheet',
    startDate: '7 Sep 2024,07.00',
    endDate: '7 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Story',
    status: "Draft",
  },
  {
    id: 12,
    title: 'PM Tools Phase 2',
    code: 'RQR012',
    activity: 'Visit',
    description: 'Asset Equipment Approval Web',
    startDate: '8 Sep 2024,07.00',
    endDate: '8 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Story',
    status: "Draft",
  },
  {
    id: 13,
    title: 'PM Tools Phase 1',
    code: 'RQR013',
    activity: 'Visit',
    description: 'Guets Approval',
    startDate: '9 Sep 2024,07.00',
    endDate: '9 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Task',
    status: "Draft",
  },
  {
    id: 14,
    title: 'Plant Maintenance',
    code: 'RQR014',
    activity: 'Visit',
    description: 'E-Kiosk 2.0',
    startDate: '10 Sep 2024,07.00',
    endDate: '10 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Task',
    status: "Draft",
  },
  {
    id: 15,
    title: 'Plant Maintenance 2',
    code: 'RQR015',
    activity: 'Visit',
    description: 'Agile Sprint',
    startDate: '11 Sep 2024,07.00',
    endDate: '11 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Issue',
    status: "Draft",
  },
  {
    id: 16,
    title: 'Plant Maintenance 3',
    code: 'RQR016',
    activity: 'Visit',
    description: 'Agile Scrum',
    startDate: '12 Sep 2024,07.00',
    endDate: '12 Sep 2024,07.00',
    participant: [{ id: 1, avatar: 'user1.jpg' }],
    linkTo: 'Issue',
    status: "Draft",
  },
]);

// const ticked = []
// const nodes = [
//   {
//     id: 1,
//     label: 'Login',
//     icon: 'mdi-login',
//     subtitle: 'IN PROGRESS (58%)',
//     status: 'IN PROGRESS (58%)',
//     statusColor: 'orange',
//     children: [
//       {
//         id: 2,
//         label: 'Module Login',
//         icon: 'mdi-view-module',
//         status: 'IN PROGRESS (58%)',
//         statusColor: 'orange',
//         children: [
//           {
//             id: 3,
//             label: 'Project',
//             icon: 'mdi-folder',
//             children: [
//               {
//                 id: 4,
//                 label: 'Login (Login)',
//                 icon: 'mdi-flag',
//                 status: 'IN PROGRESS (25%)',
//                 statusColor: 'yellow',
//               },
//               {
//                 id: 5,
//                 label: 'Reset Password (Forgot Password)',
//                 icon: 'mdi-flag',
//                 status: 'IN PROGRESS (50%)',
//                 statusColor: 'yellow',
//               },
//               {
//                 id: 6,
//                 label: 'Register Account (Register)',
//                 icon: 'mdi-flag',
//                 status: 'COMPLETE (100%)',
//                 statusColor: 'green',
//               },
//             ],
//           },
//         ],
//       },
//     ],
//   },
//   {
//     id: 7,
//     label: 'Project Summary',
//     icon: 'mdi-clipboard-list',
//     subtitle: 'COMPLETE (100%)',
//     status: 'COMPLETE (100%)',
//     statusColor: 'green',
//     children: [
//       {
//         id: 8,
//         label: 'Module Project Summary',
//         icon: 'mdi-view-module',
//         status: 'COMPLETE (100%)',
//         statusColor: 'green',
//         children: [
//           {
//             id: 9,
//             label: 'View Project (Read)',
//             icon: 'mdi-flag',
//             status: 'COMPLETE (100%)',
//             statusColor: 'green',
//           },
//           {
//             id: 10,
//             label: 'Share Project (Read)',
//             icon: 'mdi-flag',
//             status: 'COMPLETE (100%)',
//             statusColor: 'green',
//           },
//         ],
//       },
//     ],
//   },
// ]


const simple = [
  {
    label: 'Login',
    icon: 'add_box',
    status: 'IN PROGRESS (50%)',
    statusColor: 'yellow',
    children: [
      {
        label: 'Module Login',
        icon: 'add_box', // Material icon
        status: 'IN PROGRESS (50%)',
        statusColor: 'yellow',
        class: "red",
        children: [
          {
            label: 'Project', // Dropdown parent node
            icon: 'add_box',
            status: 'COMPLETE (100%)',
            statusColor: 'green',
            children: [
              {
                label: 'Login (Login)',
                status: 'IN PROGRESS (50%)',
                statusColor: 'yellow',
              },
            ],
          },
          {
            label: 'Reset Password (Forgot Password)',
            status: 'IN PROGRESS (50%)',
            statusColor: 'yellow',
          },
          {
            label: 'Register Account (Register)',
            status: 'IN PROGRESS (50%)',
            statusColor: 'yellow',
          },
        ],
      },
    ],
  },
  {
    label: 'Project Summary',
    icon: "add_box",
    status: 'IN PROGRESS (50%)',
    statusColor: 'yellow',
    children: [
      {
        label: 'Module Project Summary',
        icon: 'add_box', // Material icon
        status: 'IN PROGRESS (50%)',
        statusColor: 'yellow',
        children: [

          {
            label: 'View Project (Read)',
            status: 'IN PROGRESS (50%)',
            statusColor: 'yellow',
          },
          {
            label: 'Share Project',
            status: 'IN PROGRESS (50%)',
            statusColor: 'yellow',
          },
          {
            label: 'Project', // Dropdown parent node
            icon: 'add_box',
            status: 'IN PROGRESS (50%)',
            statusColor: 'yellow',
            children: [
              {
                label: 'Planning Project (Read)',
                status: 'IN PROGRESS (50%)',
                statusColor: 'yellow',
              },
              {
                label: 'Activities Project (Read)',
                status: 'IN PROGRESS (50%)',
                statusColor: 'yellow',
              },
            ],
          },
          {
            label: 'Epic (Read)',
            status: 'IN PROGRESS (50%)',
            statusColor: 'yellow',
          },
          {
            label: 'Performance (Read)',
            status: 'IN PROGRESS (50%)',
            statusColor: 'yellow',
          },
          {
            label: 'Sprint (Read)',
            status: 'IN PROGRESS (50%)',
            statusColor: 'yellow',
          },
        ],
      },
    ],
  },
  {
    label: 'Project',
    icon: "add_box",
    children: [
      { label: 'Add Project (Add)' }, // No icon, simple node
      { label: 'Edit Project (Add)' },
      { label: 'Delete Project (Delete)' },
    ],
  },
];



const statuses = ref([
  { label: "Group", src: "src/assets/Group.svg" },
  { label: "Module", src: "src/assets/Module.svg" },
  { label: "Feature", src: "src/assets/Feature.svg" },
])

const rowsBoard = [
  { name: 'Analyze & Design (1)' },
  { name: 'Development (2)' },
  { name: 'UAT & Release (3)' },
]

const columnsBoard = [
  { name: 'id', label: 'No', field: 'id' },
  { name: 'name', label: 'Title', field: 'name' },
  { name: 'number1', label: 'Sequence', field: 'number1' },
  { name: 'number2', label: 'Progress Weight', field: 'number2' },
  { name: 'bgColor', label: 'Color', field: 'bgColor' },
  { name: 'canretreat', label: 'Can Retreat', field: 'canretreat' },
  { name: 'haveprogress', label: 'Have Progress', field: 'haveprogress' },
  { name: 'pic', label: 'PIC', field: 'pic' },
]
const expandedData = {
  'Analyze & Design (1)': [
    { id: 1, status: 'To do', number1: 1, number2: 0, bgColor: 'bg-blue' },
    { id: 2, status: 'In Progress', number1: 2, number2: 10, bgColor: 'bg-orange' },
    { id: 3, status: 'Script Testing', number1: 3, number2: 100, bgColor: 'bg-pink' },
    { id: 4, status: 'Done', number1: 3, number2: 100, bgColor: 'bg-green' },
    { id: 5, status: 'Backlog', number1: 4, number2: 0, bgColor: 'bg-grey' }
  ],
  'Development (2)': [
    { id: 1, status: 'To do', number1: 1, number2: 0, bgColor: 'bg-blue' },
    { id: 2, status: 'Analyze', number1: 2, number2: 17, bgColor: 'bg-yellow' },
    { id: 3, status: 'Ready to Develop', number1: 3, number2: 34, bgColor: 'bg-purple' },
    { id: 4, status: 'In Progress', number1: 4, number2: 51, bgColor: 'bg-orange' },
    { id: 5, status: 'Code Review', number1: 5, number2: 68, bgColor: 'bg-pink' },
    { id: 6, status: 'SIT', number1: 6, number2: 85, bgColor: 'bg-grey' },
    { id: 7, status: 'Done', number1: 7, number2: 100, bgColor: 'bg-green' }
  ],
  'UAT & Release (3)': [
    { id: 1, status: 'To do', number1: 1, number2: 0, bgColor: 'bg-blue' },
    { id: 2, status: 'UAT', number1: 2, number2: 20, bgColor: 'bg-grey' },
    { id: 3, status: 'Ready to Release', number1: 3, number2: 40, bgColor: 'bg-purple' },
    { id: 4, status: 'Release', number1: 4, number2: 60, bgColor: 'bg-grey' },
    { id: 5, status: 'Documentation', number1: 5, number2: 80, bgColor: 'bg-pink' },
    { id: 6, status: 'Done', number1: 6, number2: 100, bgColor: 'bg-green' }
  ]
}

function getExpandedData(rowName) {
  return this.expandedData[rowName] || [];
}

const isDialogOpen = ref(false);
const selectedProject = ref('');
const showModal = ref(false)
const showBoard = ref(false)
const showEdit = ref(false)
const showProject = ref(false)
const showStekh = ref(false)
const showFilter = ref(false)
const showAdd = ref(false)
const showAct = ref(false)

// List of projects
const projects = ref([
  { label: 'Mysatnusa Redesign', value: 'mysatnusa-redesign' },
  { label: 'Project Management Agile Board 2.0', value: 'project-2' },
]);


const addProject = () => {
  console.log('Project added:', selectedProject.value);
  isDialogOpen.value = false;
};

const TypeOptions = [
  { label: 'Requirement', value: 'Requirement' },
  { label: 'Change Request', value: 'Change Request' },
  { label: 'Issue', value: 'Issue' }
]

const TipeeOptions = [
  { label: 'Group', value: 'Group' },
  { label: 'Module', value: 'Module' },
]


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

const onTypeChange = (value) => {
  if (value !== 'Change Request') {
    // Reset the dates when the status is not "Release"
    form.requirement = '';
    form.type = '';
    form.typeissue = '';
    form.issue = '';
  }
};

const onTipeeChange = (value) => {
  if (value !== 'Module') {
    form.tipe = '';
    form.module = '';
  }
};

const dialogVisible = ref(false);

const typeOptions = [
  { label: 'Requirement', value: 'Requirement' },
  { label: 'Change Request', value: 'Change Request' },
  { label: 'Issue', value: 'Issue' },
];

const roadmapsOptions = [
  { label: 'Riset pasar dan pengguna', value: 'roadmap1' },
  { label: 'Penyusunan spesifikasi dan user stories', value: 'roadmap2' },
  { label: 'Wireframing dan prototype', value: 'roadmap3' },
  { label: 'Backend (API, otentikasi, produk)', value: 'roadmap4' },
];

const issueOptions = [
  { label: 'Scope Creep', value: 'issue1' },
  { label: 'Komunikasi yang kurang efektif', value: 'issue2' },
  { label: 'Bug atau Error dalam Kode', value: 'issue3' },
  { label: 'Kurangnya Dokumentasi', value: 'issue4' },
];

const OwnerOptions = [
  { label: 'DOT', value: 'owner1' },
  { label: 'ATI', value: 'owner2' },
  { label: 'BATRE CELL', value: 'owner3' },
  { label: 'CORP SEC', value: 'owner4' },
  { label: 'FINANCE INTERNAL AUDITOR', value: 'owner5' },
  { label: 'HRD', value: 'owner6' },
];

const ProjectOptions = [
  { label: 'Mysatnusa Redesign', value: 'project1' },
  { label: 'Project Management Agile Board 1.0', value: 'project2' },
];

const StekhOptions = [
  { label: 'Ade Hilman (200546)', value: 'stekh1' },
  { label: 'Mochammad Adib Soedibyo (PKL199)', value: 'stekh2' },
  { label: 'Afridol', value: 'stekh3' },
  { label: 'Alex Sirait (200431)', value: 'stekh4' },
  { label: 'Febby Fakhrian (038886)', value: 'stekh5' },
];

const TipeOptions = [
  { label: 'Requirement', value: 'tipe1' },
  { label: 'Change Request', value: 'tipe2' },
  { label: 'Issue', value: 'tipe3' },
];

const roadOptions = [
  { label: 'Master Data Part Number', value: 'road1' },
  { label: 'Process Model', value: 'road2' },
  { label: 'Firewall Canban List', value: 'road3' },
  { label: 'Firewall Request Report', value: 'road4' },
  { label: 'Checksheet', value: 'road5' },
];

const StatsOptions = [
  { label: 'Completed', value: 'stats1' },
  { label: 'Release', value: 'stats2' },
  { label: 'Draft', value: 'stats3' },
];

const moduleOptions = [
  { label: 'Module Login', value: 'Module Login' },
  { label: 'Module Project Summary', value: 'Module Project Summary' },
  { label: 'Module Project List', value: 'Module Project List' },
  { label: 'Module Script Testing', value: 'Module Script Testing' },
  { label: 'Module Sprint Planning', value: 'Module Sprint Planning' },
];

const numberValue = ref(0);
const group = ref('op1')

const options = [
  {
    label: 'Staff',
    value: 'op1'
  },
  {
    label: 'Project Control',
    value: 'op2'
  },
  {
    label: 'Project Owner',
    value: 'op3'
  },
  {
    label: 'User',
    value: 'op4'
  },
  {
    label: 'Lead',
    value: 'op5'
  }
]

const rowss = ref([
  { id: 1, status: 'To do', number1: 1, number2: 0, bgColor: 'bg-blue' },
  { id: 2, status: 'In Progress', number1: 2, number2: 10, bgColor: 'bg-orange' },
  { id: 3, status: 'Script Testing', number1: 3, number2: 100, bgColor: 'bg-pink' },
  { id: 4, status: 'Done', number1: 3, number2: 100, bgColor: 'bg-green' },
  { id: 5, status: 'Backlog', number1: 4, number2: 0, bgColor: 'bg-grey' }
])

const treeData = [
  {
    id: 1,
    label: 'Login',
    status: 'IN PROGRESS',
    statusColor: 'orange',
    progress: '58%',
    children: [
      {
        id: 2,
        label: 'Module Login',
        status: 'IN PROGRESS',
        statusColor: 'orange',
        progress: '58%',
        children: [
          {
            id: 3,
            label: 'Project',
            status: 'COMPLETE',
            statusColor: 'green',
            progress: '100%',
            children: [
              { id: 4, label: 'Login (Login)', status: 'IN PROGRESS', statusColor: 'orange', progress: '25%' },
              { id: 5, label: 'Reset Password (Forgot Password)', status: 'IN PROGRESS', statusColor: 'orange', progress: '50%' },
              { id: 6, label: 'Register Account (Register)', status: 'COMPLETE', statusColor: 'green', progress: '100%' }
            ]
          }
        ]
      }
    ]
  },
  {
    id: 7,
    label: 'Project Summary',
    status: 'COMPLETE',
    statusColor: 'green',
    progress: '100%',
    children: [
      {
        id: 8,
        label: 'Module Project Summary',
        status: 'COMPLETE',
        statusColor: 'green',
        progress: '100%',
        children: [
          { id: 9, label: 'View Project (Read)', status: 'COMPLETE', statusColor: 'green', progress: '100%' },
          { id: 10, label: 'Share Project (Read)', status: 'COMPLETE', statusColor: 'green', progress: '100%' }
        ]
      },
      {
        id: 11,
        label: 'Project',
        status: 'COMPLETE',
        statusColor: 'green',
        progress: '100%',
        children: [
          { id: 12, label: 'Planning Project (Read)', status: 'COMPLETE', statusColor: 'green', progress: '100%' },
          { id: 13, label: 'Activities Project (Read)', status: 'COMPLETE', statusColor: 'green', progress: '100%' },
          { id: 14, label: 'Epic (Read)', status: 'COMPLETE', statusColor: 'green', progress: '100%' },
          { id: 15, label: 'Performance (Read)', status: 'COMPLETE', statusColor: 'green', progress: '100%' },
          { id: 16, label: 'Sprint (Read)', status: 'COMPLETE', statusColor: 'green', progress: '100%' }
        ]
      }
    ]
  },
  {
    id: 17,
    label: 'Project',
    status: 'NOT STARTED',
    statusColor: 'red',
    progress: '0%',
    children: [
      { id: 18, label: 'Add Project (Add)', status: 'NOT STARTED', statusColor: 'red', progress: '0%' },
      { id: 19, label: 'Edit Project (Edit)', status: 'NOT STARTED', statusColor: 'red', progress: '0%' },
      { id: 20, label: 'Delete Project (Delete)', status: 'NOT STARTED', statusColor: 'red', progress: '0%' }
    ]
  }
]

function filterMethod(node, filter) {
  return node.label.toLowerCase().includes(filter.toLowerCase());
}
</script>

<style scoped>
.red {
  background-color: #cd202e;
}

.cursor-pointer {
  cursor: pointer;
}

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

.text-subtitle2 {
  font-size: 12px;
  color: #333;
}

.text2 {
  font-size: 12px;
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

.q-tree__node--expandable {
  padding-left: 0;
}

.font-active {
  font-size: 12px;
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

.statuses-indicators {
  display: flex;
  gap: 16px;
  align-items: center;
}

.line-bottom {
  border-bottom: 1px solid #ccc;
}

.separator {
  border-top: 1px solid #ccc;
  /* Garis horizontal */
  margin-top: 16px;
  /* Jarak antara q-tree dan garis */
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

.no-background {
  background-color: transparent !important;
  border: none !important;
}

.ACTIV {
  background-color: #f2f2f2;
  border-radius: 12px;
}
</style>
