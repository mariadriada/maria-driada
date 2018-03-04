<template>
  <div class="_body">
    <div class="main_container">

      <banner :title="`${ title }`" :subtitle="`${ subtitle }`"></banner>
      <text-line :message="`${ message }`"></text-line>

      <div id="box-container">
        <div class="side left-side">
          <info-container :img="`${ img.src }`" :alt="`${ img.alt }`">
          </info-container>
        </div>

        <div class="side center-side">
          <info-container activeList="true" idData="1">
          </info-container>
        </div>

        <div class="side right-side">
          <!--
          <btn id="btn-up" name="‹"  fn="scrollDown()" link="scrollDown()" _style="transform: rotate(90deg);"></btn>
          <btn id="btn-menu" name="M" link="/menu" _style="font-size: 4rem;"></btn>
          <btn id="btn-down" name="›" link="/menu" _style="transform: rotate(90deg);"></btn>
          -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Banner from '~/components/Banner.vue'
import TextLine from '~/components/TextLine.vue'
import InfoContainer from '~/components/InfoContainer.vue'
import Btn from '~/components/Button.vue'

export default {
  components: {
    Banner,
    TextLine,
    InfoContainer,
    Btn
  },
  data () {
    return {
      title: 'Welcome!',
      subtitle: "I'm Maria Giraldo",
      message: 'I love to analyze, design and coding software',
      img: {
        src: '/img/maria_giraldo.png',
        alt: 'Maria Giraldo',
      },
      textlist:
      [
        { id: 1, text: 'frase 1', active: true, circle: true },
        { id: 2, text: 'frase 2', active: true, circle: true },
      ]
    }
  }

}
</script>

<style lang="scss">
._body {
  padding: 0;
  width: 100%;
  overflow-x: hidden;

  .main_container {
    min-width: 100%;
    height: 100vh;
    background-image: url(/img/landscape1400.jpg);
    background-size: 100% 100%;

    #box-container{
      display: flex;

      .left-side {
        width: 30%;
      }
      .center-side {
        width: 60%;
      }
      .right-side {
        width: 10%;
      }
    }
  }
}

/*
@media screen and (max-width: 48rem) {
._body{
    .main_container {
      #box-container {
        display: block;
        .side {
          width: 100%;
        }
      }
    }
  }
}*/
@media screen and (max-width: 30rem) {
._body{
    .main_container {
      #box-container {
        display: block;
        .side {
          width: 100%;
        }
      }
    }
  }
}
</style>
