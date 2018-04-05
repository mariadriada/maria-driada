<template>
  <header id="header-container">
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

#header-container {

  @include flexbox;
  @include flex-direction(column);
  @include justify-content(center);
  @include align-items(center);

  @include inherit-width;
  z-index:2;
  position: relative;
  color: #FFFDE7;
  background-color: #9C27B0;
  font-family: 'Ubuntu', sans-serif;
  background-image: url('/img/texturebkg.jpg');

/*
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
  }*/


  h1 {
    font-size: 4em;
    padding: 0.3em 0 0.001em 0;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  h2 {
    font-size: 2em;
    font-weight: 500;
    padding-bottom: .5em;
  }

}

</style>

