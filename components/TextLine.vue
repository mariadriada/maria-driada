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
  background-color: #FAFAFA;
  display: flex;
  display: ms-flexbox;
  justify-content: center;
  align-items: center;
  height: auto;
  font-size: 1rem;

  h2 {
    font-weight: 600;
    color: #F50057;
    font-size: 1.5em;
    padding: 0.5em;
  }
}

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
