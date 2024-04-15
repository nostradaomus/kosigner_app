<template>
  <section class="relative">

    <!-- Dark background -->
    <div class="absolute inset-0 bg-slate-900 pointer-events-none -z-10 [clip-path:polygon(0_0,_5760px_0,_5760px_calc(100%_-_352px),_0_100%)]" aria-hidden="true"></div>

    <div class="relative max-w-6xl mx-auto px-4 sm:px-10">
      <div class="pt-32 pb-8 md:pt-40 md:pb-32">

        <!-- Hero content -->
        <div class="max-w-xl mx-auto md:max-w-none md:flex md:items-center md:space-x-8 lg:space-x-16 xl:space-x-20 space-y-16 md:space-y-0">

          <!-- Content -->
          <div class="text-center mb-12 md:text-left md:w-[35rem]" data-aos="fade-right">
            <h1 class="font-bold text-5xl md:text-6xl leading-none tracking-tighter font-gt-america text-slate-100 mb-4">Quality tenants<br /> can come with<br /> all kinds of<br /> backgrounds.</h1>
            <p class="font-gt-america text-xl px-4 md:px-0 max-w-[450px] text-slate-100 mb-8">We help low risk, justice impacted renters get approved for homes while giving properties the assurance they need to welcome their most loyal tenants.</p>
            <div class="max-w-xs mx-auto sm:max-w-none sm:flex sm:justify-center md:justify-start space-y-4 sm:space-y-0 sm:space-x-4">
              <div>
                <router-link class="font-bold btn text-white bg-teal-600 hover:bg-teal-700 w-full group" to="/request-demo">
                  Get Notified <span class="font-bold tracking-normal text-white group-hover:translate-x-0.5 transition-transform duration-150 ease-in-out ml-1">-&gt;</span>
                </router-link>
              </div>
              <div>
                <router-link class="font-bold btn text-slate-700 bg-slate-100 hover:text-teal-600 w-full" to="/about">Learn More</router-link>
              </div>
            </div>
          </div>

          <!-- Hero image -->
          <div data-aos="fade-left">
            <!-- Image -->
            <div class="hidden md:block flex justify-center items-center">
              <div class="relative">
                <div class="absolute inset-0 pointer-events-none border-2 border-slate-100 mt-3 ml-3 translate-x-4 translate-y-4 -z-10" aria-hidden="true"></div>
                <img class="mx-auto md:max-w-none shadow-sm w-[400px] h-auto" src="../images/man-looking-out.jpg" width="540" height="405" alt="Hero" />
              </div>
              <!--
              <button class="absolute group" @click.stop="videoModalOpen = true" aria-controls="modal">
                <svg class="w-16 h-16 fill-current sm:w-20 sm:h-20 group" viewBox="0 0 88 88" xmlns="http://www.w3.org/2000/svg">
                  <circle class="text-white opacity-80 group-hover:opacity-100 transition duration-150 ease-in-out" cx="44" cy="44" r="44" />
                  <path class="text-blue-600" d="M52 44a.999.999 0 00-.427-.82l-10-7A1 1 0 0040 37V51a.999.999 0 001.573.82l10-7A.995.995 0 0052 44V44c0 .001 0 .001 0 0z" />
                </svg>
              </button>
              -->
            </div>

            <Modal id="modal" ariaLabel="modal-headline" :modalOpen="videoModalOpen" @close-modal="videoModalOpen = false">
              <video ref="video" className="w-full aspect-video" width="1920" height="1080" loop controls>
                <source src="../videos/video.mp4" type="video/mp4" />
                Your browser does not support the video tag.
              </video>
            </Modal>

          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script>
import { ref, watch } from 'vue'

import Modal from './../utils/Modal.vue'

export default {
  name: 'HeroHome',
  components: {
    Modal,
  },
  setup() {
    const videoModalOpen = ref(false)
    const video = ref(null)

    watch(videoModalOpen, () => {
      videoModalOpen.value ? video.value.play() : video.value.pause()
    })

    return {
      videoModalOpen,
      video,
    }
  }
}
</script>
