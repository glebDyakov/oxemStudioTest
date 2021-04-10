<template>
  <div class="home">
    <Header/>
    <Slider/>
    <Calculator/>
  </div>
</template>

<script>

import Header from '@/components/Header.vue'
import Calculator from '@/components/Calculator.vue'
import Slider from '@/components/Slider.vue'

export default {
  name: 'Home',
  components: {
    Header,
    Calculator,
    Slider
  }
}
</script>
