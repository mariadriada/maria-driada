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
<!--
    <nav class="content nav">
      <main-menu/>
    </nav>-->

  </header>
</template>

<script>
import MainMenu from '~/components/menu/Menu.vue'
import BasicMenu from '~/components/menu/BasicMenu.vue'

export default {
  components: {
    MainMenu,
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

  width: 100%;
  height: auto;
  //height: 25vh;
  //background-color: #4FC3F7;
 // display: flex;

  font-size: 1rem;
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
      //height: 50%;
      padding: 0.5em 2em 0 0;
      text-align: right;

      @include flexbox;
    //  @include justify-content(flex-end);
      @include flex-direction(column);

      h1 {
        color: #FAFAFA;
        font-weight: 100;
        font-size: 1.6em;
      //padding-top:0.5em;
        font-family: 'Orbitron', sans-serif;
      }

      h2{
        width:70%;
        margin-left: 30%;
        color: #FFFF00;
        font-weight: 200;
        font-style: oblique;
        font-size: 1.1em;
        font-family: 'Raleway', sans-serif;
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

@media screen and (min-width: 48rem) {
  #menu-top {
   // margin-top: -3rem;
   // background-color: #4FC3F7;
  }
}

@media screen and (max-width: 48rem) {
  #header2-container {
    font-size: .5rem;

    #menu-top {
      background-color:red;
      margin-top: -2.5rem;
      //font-size: 1rem;
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
