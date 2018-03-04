<template>
  <div class="header2-container"">
    <div class="profile">
      <figure>
        <nuxt-link to="/about"><img :src="`${ img }`" :alt="`${ alt }`" /></nuxt-link>
      </figure>
    </div>
    <div class="container">
      <div class="text">
        <h1> {{ text1 }} </h1>
        <h2> {{ text2 }}</h2>
      </div>
      <div class="text">
        <main-menu/>
      </div>
    </div>
  </div>
</template>

<script>
import MainMenu from '~/components/menu/Menu.vue'

export default {
  components: {
    MainMenu
  },
  data() {
    return {
      text1: 'Maria Eugenia Giraldo Forero',
      text2: 'Business Analyst and Software Developer',
      img: '/img/profile.png',
      alt: 'Maria Eugenia Giraldo Forero'

    }
  }
}
</script>

<style lang="scss">
.header2-container {
  min-width: 100%;
  height: 25vh;
  background-color: #F50057;
  display: flex;
  font-size: 1rem;

  .profile {
    width:30%;
    //border: 1px solid black;
    height: inherit;
    padding: 0.2em 0 0 3em;

    figure{
      width: 10rem;
      height: 10rem;
      background-color: #FAFAFA;
      border-radius: 50% 50%;
      display: block;

      img {
        width: 8rem;
        display: block;
        margin: 0 auto;
      }
    }


  }
  .container{
    width:70%;
    height: inherit;
    font-size: 1rem;

    div {
      width:100%;
      height: 50%;

      h1,h2{
         padding: 0 3rem 0 0;
         text-align: right;
      }

      h1 {
        color: #FAFAFA;
        font-weight: 600;
        font-size: 1.6em;
        text-decoration: underline;
        padding-top:0.5rem;
      }

      h2{
        color: #FFFF00;
        font-weight: 400;
        font-style: oblique;
        font-size: 1.1em;
      }
    }
  }
}
</style>
