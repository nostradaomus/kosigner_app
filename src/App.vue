<template>
  <router-view />
</template>

<script>
import AOS from 'aos'
import './charts/ChartjsConfig';

export default {
  mounted() {
    AOS.init({
      once: true,
      disable: 'phone',
      duration: 500,
      easing: 'ease-out-cubic',
    })
  }
}
</script>


