<template>
<div class="header-container">
    <h1 v-if="title"> {{ title }} </h1>
    <h2 v-if="subtitle"> {{ subtitle }} </h2>
</div>
</template>

<script>
export default {
  props: ['title', 'subtitle']
}
</script>

<style lang="scss">
.header-container {
  min-width: 100%;
  min-height: 25vh;
  min-height: auto;
  text-align: center;
  color: #FAFAFA;
  position: relative;
  z-index:2;
  font-size: 1rem;

  ::before{
    content: "";
    position: absolute;
    z-index: -1;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: #2196F3;
    opacity: .1;
    filter: alpha(opacity=1000);
  }

  h1{
    font-size: 4em;
    padding: 0.3em 0 0.001em 0;
    color: #4A148C;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }
  h2{
    font-size: 2em;
    font-weight: 500;
  }
}

@media  (max-width: 48rem) {
  .header-container  {
      font-size: .9rem;
  }
}

@media  (max-width: 30rem) {
  .header-container  {
      font-size: .8rem;
      h1 {
         letter-spacing:0;
      }
  }
}

@media screen and (min-width: 105rem) {
  .header-container  {
     font-size: 1.5rem;
     background-color:blue;
  }
}
</style>

