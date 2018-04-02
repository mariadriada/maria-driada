<template>
  <div class="text-line">
    <h2> {{ message }} </h2>
  </div>
</template>

<script>

export default {
  props: ['message']
}

</script>

<style lang="scss">

.text-line {

  @include inherit-width;
  @include flexbox;
  @include justify-content(center)
  @include align-items(center)

  min-height: 7vh;
  text-align: center;
  background-color: #FFF176;
  height: auto;
  transition:all 0.3s ease;

  h2 {
    font-weight: 300;
    color: #03A9F4;
    font-size: 1.7em;
    padding: 0.5em;
    letter-spacing: 0.1em;
  }

  &.sub {
    background-color: #FAFAFA;

    h2 {
      padding: 2rem 0 2rem 0;
      letter-spacing: 0.09em;
    }
  }
}

</style>
