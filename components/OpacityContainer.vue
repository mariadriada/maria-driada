<template>
  <div class="opacity-container">
    <p>{{ text }}</p>
  </div>
</template>

<script>

export default {
  props: ['text']

}

</script>


<style lang="scss">

.opacity-container {
  width: 100%;
  heigh: auto;
  position: relative;
  z-index: 1;
  display: flex;
  display: -ms-flex;
  display: -webkit-flex;
  display: -moz-flex;
  align-items: center;
  -webkit-align-items: center;
  font-size: 1rem;


  p {
    width: inherit;
    color: #FFF176;
    font-size: 1.7em;
    text-align: center;
    padding: 2em;
  }

  @mixin opacitfix($opacity: 0.1 , $bgcolor: #FFF176 ) {

    @if $opacity > 0 {

      ::before {
        content: "";
        position: absolute;
        z-index: -1;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: $bgcolor;
        opacity: $opacity;
        filter: alpha(opacity = $opacity * 1000 );
        khtml-opacity:  $opacity;
        -moz-opacity: $opacity;
      }
    }

  }

  &.default {
    @include opacitfix();

    p {
      color: #FAFAFA;
      font-weight: 600;
      letter-spacing: 1px;
    }
  }

  &.blue {
    background-color: #4FC3F7;
  }

  &.center {
    display: block;
    margin: 0 auto;
  }

}

// Media query

@media screen and (max-width: 48rem) {
  .opacity-container {
    font-size: .7rem;
  }
}

</style>
