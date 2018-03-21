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

  min-width: 100%;
  min-height: 7vh;
  text-align: center;
  background-color: #FFF176;
  display: flex;
  display: ms-flexbox;
  justify-content: center;
  align-items: center;
  height: auto;
  font-size: 1rem;
  font-family: 'Orbitron', sans-serif;
  transition:all 0.3s ease;

  h2 {
    font-weight: 300;
    color: #03A9F4;
    font-size: 1.5em;
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

//Media queries

@media screen and (max-width: 48rem) {
  .text-line {
     font-size: .9rem;
  }
}

@media screen and (max-width: 30rem) {
  .text-line {
     font-size: .7rem;
  }
}

</style>
