<template>
  <div class="flex h-[100dvh] overflow-hidden">

    <!-- Sidebar -->
    <Sidebar :sidebarOpen="sidebarOpen" @close-sidebar="sidebarOpen = false" />

    <!-- Content area -->
    <div class="relative flex flex-col flex-1 overflow-y-auto overflow-x-hidden">

      <!-- Site header -->
      <Header :sidebarOpen="sidebarOpen" @toggle-sidebar="sidebarOpen = !sidebarOpen" />

      <main class="grow">
        <div class="px-4 sm:px-6 lg:px-8 py-8 w-full max-w-9xl mx-auto">

          <!-- Welcome banner -->
          <WelcomeBanner />

          <!-- Dashboard actions -->
          <div class="sm:flex sm:justify-between sm:items-center mb-8">

            <!-- Left: Avatars -->
            <DashboardAvatars />

            <!-- Right: Actions -->
            <div class="grid grid-flow-col sm:auto-cols-max justify-start sm:justify-end gap-2">

              <!-- Datepicker built with flatpickr -->
              <Datepicker align="right" />
              <!-- Add view button -->
              <button class="btn bg-teal-600 hover:bg-teal-700 text-white">
                <svg class="w-4 h-4 fill-current opacity-50 shrink-0" viewBox="0 0 16 16">
                  <path d="M15 7H9V1c0-.6-.4-1-1-1S7 .4 7 1v6H1c-.6 0-1 .4-1 1s.4 1 1 1h6v6c0 .6.4 1 1 1s1-.4 1-1V9h6c.6 0 1-.4 1-1s-.4-1-1-1z" />
                </svg>
                <span class="hidden xs:block ml-2">Invite Applicant</span>
              </button>
            </div>

          </div>

          <!-- Cards -->
          <div class="grid grid-cols-12 gap-6">
            <!-- Card (Recent Activity) -->
            <DashboardCard10 />
            <!-- Post 2 -->
            <div class="bg-white dark:bg-slate-800 shadow-md rounded border border-slate-200 dark:border-slate-700 px-5 col-span-full xl:col-span-6 bg-white dark:bg-slate-800 shadow-lg rounded-sm border border-slate-200 dark:border-slate-700">
              <header class="py-4 border-b border-slate-100 dark:border-slate-700">
                <h2 class="font-semibold text-slate-800 dark:text-slate-100">News</h2>
              </header>
              <!-- Header -->
              <header class="flex justify-between items-start space-x-3 my-3">
                <!-- User -->
                <div class="flex items-start space-x-3">
                  <img class="rounded-full shrink-0" src="../images/user-40-06.jpg" width="40" height="40" alt="User 06" />
                  <div>
                    <div class="leading-tight">
                      <a class="text-sm font-semibold text-slate-800 dark:text-slate-100" href="#0">Kosigner AI</a>
                    </div>
                    <div class="inline-flex items-center">
                      <svg class="w-3 h-3 shrink-0 fill-yellow-500 mr-1" xmlns="http://www.w3.org/2000/svg">
                        <path d="M11.953 4.29a.5.5 0 0 0-.454-.29H6.14L6.984.62A.5.5 0 0 0 6.12.174l-6 7A.5.5 0 0 0 .499 8h5.359l-.844 3.38a.5.5 0 0 0 .864.445l6-7a.5.5 0 0 0 .075-.534Z" />
                      </svg>
                      <div class="text-xs text-slate-500">Sponsored</div>
                    </div>
                  </div>
                </div>
              </header>
              <!-- Body -->
              <div class="text-sm text-slate-800 dark:text-slate-100 space-y-2 mb-5">
                <p>Your year in review, co-authored by the Kosigner AI.</p>
                <div class="relative !my-4">
                  <img class="block w-full" src="../images/interior5.jpg" width="590" height="332" alt="Feed 01" />
                  <div class="absolute left-0 right-0 bottom-0 p-4 bg-black bg-opacity-25 backdrop-blur-md">
                    <div class="flex items-center justify-between">
                      <div class="text-xs font-medium text-slate-300">kosigner.com</div>
                      <a class="text-xs font-medium text-indigo-400 hover:text-indigo-300" href="#0">Learn More -&gt;</a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- Line chart (Acme Plus) -->
            <DashboardCard01 />
            <!-- Line chart (Acme Advanced) -->
            <DashboardCard02 />
            <!-- Line chart (Acme Professional) -->
            <DashboardCard03 />
            <!-- Bar chart (Direct vs Indirect) -->
            <DashboardCard04 />
            <!-- Line chart (Real Time Value) -->
            <DashboardCard05 />
            <!-- Doughnut chart (Top Countries) -->
            <DashboardCard06 />
            <!-- Table (Top Channels) -->
            <DashboardCard07 />
            <!-- Line chart (Sales Over Time) -->
            <DashboardCard08 />
            <!-- Stacked bar chart (Sales VS Refunds) -->
            <DashboardCard09 />

          </div>

        </div>
      </main>

    </div>

  </div>
</template>

<script>
import { ref } from 'vue'
import Sidebar from '../partials/Sidebar.vue'
import Header from '../partials/Header.vue'
import WelcomeBanner from '../partials/dashboard/WelcomeBanner.vue'
import DashboardAvatars from '../partials/dashboard/DashboardAvatars.vue'
import FilterButton from '../components/DropdownFilter.vue'
import Datepicker from '../components/Datepicker.vue'
import DashboardCard01 from '../partials/dashboard/DashboardCard01.vue'
import DashboardCard02 from '../partials/dashboard/DashboardCard02.vue'
import DashboardCard03 from '../partials/dashboard/DashboardCard03.vue'
import DashboardCard04 from '../partials/dashboard/DashboardCard04.vue'
import DashboardCard05 from '../partials/dashboard/DashboardCard05.vue'
import DashboardCard06 from '../partials/dashboard/DashboardCard06.vue'
import DashboardCard07 from '../partials/dashboard/DashboardCard07.vue'
import DashboardCard08 from '../partials/dashboard/DashboardCard08.vue'
import DashboardCard09 from '../partials/dashboard/DashboardCard09.vue'
import DashboardCard10 from '../partials/dashboard/DashboardCard10.vue'
import DashboardCard11 from '../partials/dashboard/DashboardCard11.vue'

export default {
  name: 'Dashboard',
  components: {
    Sidebar,
    Header,
    WelcomeBanner,
    DashboardAvatars,
    FilterButton,
    Datepicker,
    DashboardCard01,
    DashboardCard02,
    DashboardCard03,
    DashboardCard04,
    DashboardCard05,
    DashboardCard06,
    DashboardCard07,
    DashboardCard08,
    DashboardCard09,
    DashboardCard10,
    DashboardCard11,
  },
  setup() {

    const sidebarOpen = ref(false)

    return {
      sidebarOpen,
    }
  }
}
</script>
