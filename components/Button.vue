<template>
  <div class="button">
<!--<nuxt-link to="`${ link }`" :style="`${_style }`" v-if="link" >{{ name }}</nuxt-link>-->
     <div v-on:click="scrollDown" >{{ name }}hh</div>
  </div>
</template>

<script>
export default {
  props: ['name', 'link', '_style', 'fn'],
  methods: {
    scrollDown () {
      console.log('scroll');
      this.fn
    }
  }
}
</script>

<style lang="scss">
.button {
  text-align: center;
  font-size: 10rem;

  a{
    text-decoration: none;
  }

}

</style>
