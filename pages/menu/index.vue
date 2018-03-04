<template>
  <div class="menu-container">
    <banner class="header2-container"">
    </banner>
    <div class="data-container">
      <div class="dinamic-text">
        dinamic text
      </div>
    </div>
  </div>
</template>

<script>
import Banner from '~/components/Banner2.vue'

export default {
  components: {
    Banner
  }
}


</script>

<style lang="scss">
.menu-container {
  background-color: #F50057;
  min-height: 100vh;

  .data-container {
    min-height: 60vh;
    height: 60vh;
    max-height: auto;
    background-color:  #FAFAFA;

    .dinamic-text {
      width: 90%;
      height: inherit;
      background-color:  transparent;
      margin: 0 auto;

    }
  }
}
</style>
