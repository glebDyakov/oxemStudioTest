<template>
  <div>
    <span class="badge rounded-pill bg-light text-dark">
      <label for="customRange3" class="form-label">{{ currentPrice }}</label><br/>
      <input ref="inputRange" v-model="currentPrice" @change="refreshPrice($event)" type="range" class="form-range" min="0" max="3300000" step="330000" id="customRange3">
      <input type="number" ref="currentPriceRef" v-model="currentPrice" @input="refreshPrice($event)" @blur="focusField" class="currentPriceNumberField" min="0" max="3300000">
    </span>
  </div>
</template>

<script>
export default {
  name: 'Calculator',
  data(){
    return {
      currentPrice: 0
    }
  },
  mounted(){
    this.focusField()
  },
  methods: {
    refreshPrice(event){
      if(this.currentPrice > 3300000){
        this.currentPrice = 3300000
      } else if(this.currentPrice < 0){
        this.currentPrice = 0
      }
    },

    focusField(){
      this.$refs.currentPriceRef.focus()
    }
  }
}
</script>
<style scoped>
  .currentPriceNumberField {
    color: transparent;
    border: 0px solid transparent;
    outline: 0px solid transparent;
  }
</style>