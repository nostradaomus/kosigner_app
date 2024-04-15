<template>
  <header class="absolute w-full z-30 mt-2" :class="{ 'dark': mode !== 'light' }">
    <div class="max-w-6xl mx-auto pt-2 pr-4 md:px-4">
      <div class="flex items-center justify-between h-16 md:h-20">

        <!-- Site branding -->
        <div class="shrink-0 mr-4">
          <!-- Logo -->
        <router-link class="block" to="/">
          <img class="h-20" src="../images/kosigner.png" alt="kosigner logo" />
        </router-link>
        </div>

        <!-- Desktop navigation -->
        <nav class="hidden md:flex md:grow">

          <!-- Desktop menu links -->
          <ul class="flex grow justify-start flex-wrap items-center">
            <li>
              <router-link to="/about" class="font-medium text-slate-800 hover:text-slate-100 dark:text-slate-300 dark:hover:text-white px-3 lg:px-5 py-2 flex items-center transition duration-150 ease-in-out">About</router-link>
            </li>
            <li>
              <router-link to="/updates" class="font-medium text-slate-800 hover:text-slate-100 dark:text-slate-300 dark:hover:text-white px-3 lg:px-5 py-2 flex items-center transition duration-150 ease-in-out">Updates</router-link>
            </li>
            <li>
              <router-link to="/case-study" class="font-medium text-slate-800 hover:text-slate-100 dark:text-slate-300 dark:hover:text-white px-3 lg:px-5 py-2 flex items-center transition duration-150 ease-in-out">Case Study</router-link>
            </li>
            <!--
            <li>
              <router-link to="/pricing" class="font-medium text-slate-800 hover:text-blue-600 dark:text-slate-300 dark:hover:text-white px-3 lg:px-5 py-2 flex items-center transition duration-150 ease-in-out">Pricing</router-link>
            </li>
            <li>
              <router-link to="/blog" class="font-medium text-slate-800 hover:text-blue-600 dark:text-slate-300 dark:hover:text-white px-3 lg:px-5 py-2 flex items-center transition duration-150 ease-in-out">Blog</router-link>
            </li>
            <li>
              <router-link to="/customers" class="font-medium text-slate-800 hover:text-blue-600 dark:text-slate-300 dark:hover:text-white px-3 lg:px-5 py-2 flex items-center transition duration-150 ease-in-out">Our Community</router-link>
            </li>
            <Dropdown title="Resources">
              <li>
                <router-link to="/case-study" class="font-medium text-sm text-slate-600 hover:text-teal-600 flex py-2 px-5 leading-tight">Case Study</router-link>
              </li>
              <li>
                <router-link to="/support" class="font-medium text-sm text-slate-600 hover:text-teal-600 flex py-2 px-5 leading-tight">Support center</router-link>
              </li>
            </Dropdown>
            -->
          </ul>

          <!-- Desktop sign in links -->
          <ul class="flex grow justify-end flex-wrap items-center pr-6">
            <img class="mt-2 w-[8rem] h-auto" src="../images/coming-soon.png" width="540" height="405" alt="Hero" />
            <!--
            <li>
              <router-link to="/signin" class="font-medium text-slate-800 hover:text-blue-600 dark:text-slate-300 dark:hover:text-white px-3 lg:px-5 py-2 flex items-center transition duration-150 ease-in-out">Sign in</router-link>
            </li>
            <li>
              <router-link to="/onboarding-01" class="font-medium text-blue-600 dark:text-slate-300 dark:hover:text-white px-3 lg:px-5 py-2 flex items-center transition duration-150 ease-in-out group">Get started<span class="tracking-normal text-teal-600 font-bold group-hover:translate-x-0.5 transition-transform duration-150 ease-in-out ml-1">-&gt;</span></router-link>
            </li>
            -->
          </ul>

        </nav>

        <!-- Mobile menu -->
        <div class="flex md:hidden">

          <!-- Hamburger button -->
          <button class="hamburger" ref="hamburger" :class="{ active: mobileNavOpen }" aria-controls="mobile-nav" :aria-expanded="mobileNavOpen" @click="mobileNavOpen = !mobileNavOpen">
            <span class="sr-only">Menu</span>
            <svg class="w-6 h-6 fill-current text-slate-900 dark:text-slate-100" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <rect y="4" width="24" height="2" />
              <rect y="11" width="24" height="2" />
              <rect y="18" width="24" height="2" />
            </svg>
          </button>

          <!-- Mobile navigation -->
          <transition
            enter-active-class="transition ease-out duration-200 transform"
            enter-from-class="opacity-0 -translate-y-2"
            enter-to-class="opacity-100 translate-y-0"
            leave-active-class="transition ease-out duration-200"
            leave-from-class="opacity-100"
            leave-to-class="opacity-0"
          >
            <nav
              id="mobile-nav"
              ref="mobileNav"
              v-show="mobileNavOpen"
              class="absolute top-full h-screen pb-16 z-20 left-0 w-full overflow-scroll no-scrollbar bg-white"
            >
              <ul class="px-5 py-2">
                <li>
                  <router-link to="/about" class="flex font-medium text-slate-800 hover:text-teal-600 py-2">About</router-link>
                </li>
                <li>
                  <router-link to="/updates" class="flex font-medium text-slate-800 hover:text-teal-600 py-2 pb-3">Updates</router-link>
                </li>
                <li>
                  <router-link to="/case-study" class="flex font-medium text-slate-800 hover:text-teal-600 py-2">Case Study</router-link>
                </li>
                <!--
                <li>
                  <router-link to="/pricing" class="flex font-medium text-slate-800 hover:text-blue-600 py-2">Pricing</router-link>
                </li>
                <li>
                  <router-link to="/blog" class="flex font-medium text-slate-800 hover:text-blue-600 py-2">Blog</router-link>
                </li>
                <li>
                  <router-link to="/wall-of-love" class="flex font-medium text-slate-800 hover:text-blue-600 py-2">Wall of Love</router-link>
                </li>
                <li class="py-2 my-2 border-t border-b border-slate-200">
                  <span class="flex font-medium text-slate-800 hover:text-blue-600 py-2">Resources</span>
                  <ul class="pl-4">
                    <li>
                      <router-link to="/404" class="text-sm flex font-medium text-slate-600 hover:text-blue-600 py-2">404</router-link>
                    </li>
                    <li>
                      <router-link to="/support" class="text-sm flex font-medium text-slate-600 hover:text-blue-600 py-2">Support</router-link>
                    </li>
                  </ul>
                </li>
                <li>
                  <router-link to="/signin" class="flex font-medium w-full text-slate-800 hover:text-blue-600 py-2">Sign in</router-link>
                </li>
                -->
                <li>
                  <router-link to="/request-demo" class="flex border-t border-b border-slate-200 font-medium text-teal-600 py-2 group">Get Notified <span class="tracking-normal text-teal-600 group-hover:translate-x-0.5 transition-transform duration-150 ease-in-out ml-1">-&gt;</span></router-link>
                </li>
              </ul>
            </nav>
          </transition>

        </div>

      </div>
    </div>
  </header>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue'
import Dropdown from './../utils/Dropdown.vue'

export default {
  name: 'Header',
  props: ['mode'],
  components: {
    Dropdown,
  },
  setup() {

    const mobileNavOpen = ref(false)
    const mobileNav = ref(null)
    const hamburger = ref(null)

    // close on click outside
    const clickHandler = ({ target }) => {
      if (!mobileNavOpen.value || mobileNav.value.contains(target) || hamburger.value.contains(target)) return
      mobileNavOpen.value = false
    }

    // close if the esc key is pressed
    const keyHandler = ({ keyCode }) => {
      if (!mobileNavOpen.value || keyCode !== 27) return
      mobileNavOpen.value = false
    }

    onMounted(() => {
      document.addEventListener('click', clickHandler)
      document.addEventListener('keydown', keyHandler)
    })

    onUnmounted(() => {
      document.removeEventListener('click', clickHandler)
      document.removeEventListener('keydown', keyHandler)
    })

    return {
      mobileNavOpen,
      mobileNav,
      hamburger,
    }
  }
}
</script>
