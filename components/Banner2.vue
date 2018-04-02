<template>
  <header id="header2-container">

    <section id="section1">

      <div id="profile">
        <figure>
          <nuxt-link to="/about"><img :src="`${ img }`" :alt="`${ alt }`" /></nuxt-link>
        </figure>
      </div>

      <hgroup id="content">
        <h1> {{ text1 }} </h1>
        <h2> {{ text2 }}</h2>
      </hgroup>

    </section>

    <nav id="menu-top"> <basic-menu/></nav>

  </header>
</template>

<script>

import BasicMenu from '~/components/menu/BasicMenu.vue'

export default {

  components: {
    BasicMenu
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

#header2-container {

  @include inherit-width;
  height: auto;
  position: fixed;
  z-index: 2;

  section {

    @include flexbox;
    background-color: #4FC3F7;
    height: auto;

    #profile {
      width: 40%;
      height: inherit;
      padding: .5em 0 .5em 2em;

      figure{
        width: 10em;
        height: 10em;
        background-color: #FAFAFA;
        border-radius: 50% 50%;
        display: block;

        img {
          width: 8em;
          display: block;
          margin: 0 auto;
          border: 0;
        }
      }
    }

    hgroup {
      width:60%;
      padding: 0.5em 2em 0 0;
      text-align: right;

      @include flexbox;
      @include flex-direction(column);

      h1 {
        color: #FAFAFA;
        font-weight: 100;
        font-size: 1.6em;
      }

      h2{
        margin-left: 30%;
        color: #FFFF00;
        font-weight: 200;
        font-style: oblique;
        font-size: 1.1em;
      }
    }
  }

  nav {
    padding-right: 2em;
    margin-top: -3rem;
    background-color: #4FC3F7;

    li {
      a {
        color: #FAFAFA;

        &:hover {
          @include active;
        }
      }
    }
  }
}


//Media queries


@media screen and (max-width: 48rem) {
  #header2-container {

    #menu-top {
      margin-top: -2.5rem;
    }
  }

}

@media screen and (max-width: 30rem) {
  #header2-container {
    #menu-top {
      margin-top: -2rem;
    }
  }
}


@media screen and (max-width: 20rem) {
  #header2-container {

    section {
      hgroup {
         @include justify-content(space-around);
         padding-top:0;
      }
    }

    #menu-top {
      margin-top: 0;
      background-color: #AA00FF;
    }

  }
}

</style>
