<template>
  <li
    class="relative"
    @mouseenter="dropdownOpen = true"
    @mouseleave="dropdownOpen = false"
    @focusin="dropdownOpen = true"
    @focusout="dropdownOpen = false"
  >
    <a
      class="font-medium text-slate-800 dark:text-slate-300 dark:hover:text-white px-3 lg:px-5 py-2 flex items-center transition duration-150 ease-in-out"
      href="#0"
      aria-haspopup="true"
      aria-expanded={dropdownOpen}
      @click.prevent
    >
      {{title}}
      <svg class="w-3 h-3 fill-current text-slate-400 dark:text-teal-600 cursor-pointer ml-1 shrink-0" viewBox="0 0 12 12" xmlns="http://www.w3.org/2000/svg">
        <path d="M10.28 4.305L5.989 8.598 1.695 4.305A1 1 0 00.28 5.72l5 5a1 1 0 001.414 0l5-5a1 1 0 10-1.414-1.414z" />
      </svg>
    </a>
    <transition
      enter-active-class="transition ease-out duration-200 transform"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition ease-out duration-200"
      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
    >
      <ul v-show="dropdownOpen" class="origin-top-right absolute top-full right-0 w-40 bg-white py-2 ml-4 rounded shadow-lg">
        <slot />
      </ul>
    </transition>
  </li>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Dropdown',
  props: ['title'],
  setup() {

    const dropdownOpen = ref(null)

    return {
      dropdownOpen,
    }
  }
}
</script>
