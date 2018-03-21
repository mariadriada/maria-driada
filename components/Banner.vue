<template>
  <header class="header-container show">
      <h1 v-if="title"> {{ title }} </h1>
      <h2 v-if="subtitle" > {{ subtitle }} </h2>
  </header>
</template>

<script>

export default {
  props: ['title', 'subtitle']
}

</script>

<style lang="scss">

$opacity: 0.3;

.header-container {

  min-width: 100%;
  text-align: center;
  z-index:2;
  font-size: 1rem;
  position: relative;
  color: #9C27B0;
  display: block;
  background-color: transparent;

  ::before {
    width: 100%;
    content: "";
    position: absolute;
    z-index: -1;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: #FFF176;
    opacity: $opacity;
    filter: alpha(opacity = $opacity*1000);
    khtml-opacity: $opacity;
    -moz-opacity: $opacity;
  }

  h1 {
    font-size: 4em;
    padding: 0.3em 0 0.001em 0;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    font-family: 'Orbitron', sans-serif;
  }

  h2 {
    font-size: 2em;
    font-weight: 500;
    padding-bottom: .5em;
  }

}

//Media queries

@media screen and (max-width: 48rem) {
  .header-container  {
      font-size: .9rem;
  }
}

@media screen and (max-width: 30rem) {
  .header-container  {

    height: 17vh;
    font-size: .7rem;

    h1 {
        letter-spacing:0;
    }
  }
}

@media screen and (min-width: 105rem) {
  .header-container  {
     font-size: 1.5rem;
  }
}

</style>

