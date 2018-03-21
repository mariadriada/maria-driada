<template>
  <div class="_body">

    <!-- main-container -->
    <div class="main-container">

      <!-- screen -->
      <div class="screen">
        <banner :title="`${ title }`" :subtitle="`${ subtitle }`"></banner>
        <text-line :message="`${ message }`" id="fixed" class=" budge-left"></text-line>

        <!--box-container-->
        <div id="box-container" class="box-container budge-right">
          <div class="side left-side">
            <info-container :img="`${ img.src }`" :alt="`${ img.alt }`">
            </info-container>
          </div>

          <div class="side center-side" >
            <info-container activeList="true" idData="1">
            </info-container>
          </div>

            <!-- TODO <div class="button button-down"><icon name="angle-down" scale="4"  ></icon></div>-->
            <div v-on:click="scrollTop" class="button button-up" id="button-up">
              <icon name="angle-up" scale="4" ></icon>
            </div>

            <div class="button button-right hidden" id="button-right">
              <nuxt-link to="/menu">
                <icon name="angle-right" scale="4"></icon>
              </nuxt-link>
            </div>
        </div>
        <!-- /box-container -->

      </div>
      <!-- /screen -->

      <!-- next-container -->
      <div class="next-container">
        <text-line :message="`${profession.title}`" class="sub"></text-line>

        <div class="block">
          <div class="side middle middle1">
            <info-container activeList="true" idData="2" class="data2">
            </info-container>
          </div>

          <div class="side middle description">
            <opacity-container :text="`${profession.text1}`" class="blue ">
            </opacity-container>
          </div>
        </div>

        <div class="block b1">
           <opacity-container :text="`${profession.text2}`" class="default center">
            </opacity-container>
        </div>
      </div>
      <!-- next-container -->

    <footer-div/>

    </div>
    <!-- /main-container -->
  </div>
  <!-- /_body -->
</template>

<script>

import Banner from '~/components/Banner.vue'
import TextLine from '~/components/TextLine.vue'
import InfoContainer from '~/components/InfoContainer.vue'
import FooterDiv from '~/components/Footer.vue'
import OpacityContainer from '~/components/OpacityContainer.vue'

//vue-awesome plugin import
import "vue-awesome/icons/angle-up"
//import "vue-awesome/icons/angle-down" //TODO
import "vue-awesome/icons/angle-right"
import Icon from 'vue-awesome/components/Icon.vue'

export default {

  components: {
    Banner,
    TextLine,
    InfoContainer,
    OpacityContainer,
    Icon,
    FooterDiv
  },

  data () {
    return {
      title: 'Welcome!',
      subtitle: "I'm Maria Giraldo",
      message: 'I love to analyze and software coding!',
      img: {
        src: '/img/mariagiraldo.png',
        alt: 'Maria Giraldo',
      },
      textlist:
      [
        { id: 1, text: 'frase 1', active: true, circle: true },
        { id: 2, text: 'frase 2', active: true, circle: true },
      ],
      profession: {
        title: `Maria´s profession`,
        text1: `I’m a person interested in the technology, the software architecture,
                      the planning of projects and work by objectives.`,
        text2: 'Responsible and dedicated to knowledge that I have no.',

      }
    }
  },

  methods: {

    scrollTop () {
      let html = document.documentElement
      let to = document.documentElement.scrollTop

      if (to <= 0) return

      let _self = this

      setTimeout(function(){
        console.log('this', this)
        html.scrollTop = to -20
        _self.$emit('scrollTop')
      },10)

    },

    scroll(event) {

      const scroll = document.documentElement.scrollTop
      let textelement = document.getElementById('fixed')
      let buttonup = document.getElementById('button-up')

      // Apply effects when scrolling
      if ( scroll >= 135 ) {
        textelement.classList.remove("budge-left");
        textelement.classList.add("fixed");

        buttonup.classList.remove('hidden')
        buttonup.classList.add('visible')

        if ( scroll > 400 ) {
          let buttonright = document.getElementById('button-right')

          if( !buttonright.classList.contains('visible') ) {
            buttonright.classList.remove('hidden')
            buttonright.classList.add('visible')
          }
        }
      }
      else {
        textelement.classList.remove('fixed')

        buttonup.classList.add('hidden')
        buttonup.classList.remove('visible')
      }
    }
  },
  mounted () {

    document.getElementById('button-up').classList.add('hidden')

    //Event listeners
    document.addEventListener('scroll', this.scroll)
    this.$on('scrollTop', this.scrollTop)
    this.$on('scrollDown', this.scrollDown)
  }
}
</script>

<style lang="scss">
._body {

  padding: 0;
  width: 100%;

  .main-container {

    min-width: 100%;
    height: auto;
    background-size: 100% 100%;
    cursor: default;
    font-family: 'Ubuntu', sans-serif;
    padding: 0;
    margin: 0;
    overflow: hidden;

    .screen {
      background-image: url('/img/bg1400.jpg');
      background-attachment: fixed;
      background-size: cover;
      height: inherit;
      padding:0;
      margin: 0;
    }

    .box-container {

      display: flex;
      display: -ms-flex;
      display: -webkit-flex;
      visibility: hidden;
      height: auto;

      .left-side {
        width: 35%;
      }
      .center-side {
        width: 65%;
      }

      //buttons appearance
      .button {
        color: #9C27B0;
        cursor: pointer;
      }
      .button-up {
        position: fixed;
        top: 80vh;
        right: 2%;
        z-index: 5;
      }
      .button-down {
        position: fixed;
        top: 50vh;
        right: 2%;
        z-index: 5;
      }
      .button-right {
        position: fixed;
        top: 5vh;
        right: 3%;
        z-index: 5;
        color:red;
      }
      a:visited {
        color: #9C27B0;
      }
      a:line {
        color: #9C27B0;
      }

    }

    .next-container {

      width: 100%;
      height: auto;

      .block {
        width:100%;
        display: flex;
        display: -ms-flex;
        display: -webkit-flex;
        display: -moz-flex;

        .middle {
          width:50%;
          height: inherit;
          display: flex;
          display: -ms-flex;
          display: -webkit-flex;
          display: -moz-flex;
        }

        .middle1 {
          background-color: #FAFAFA;
        }
      }
      .b1 {
        background-image: url('/img/line.jpg');
      }

    }

    .fixed {

      position: fixed;
      top: 0;
      z-index: 3;
      -webkit-animation: swingY .3s ease-in-out;
      animation: swingY .3s ease-in-out;
      -webkit-animation-iteration-count: 1;
      animation-iteration-count: 1;
      padding: .5em;

      h2 {
        color: #9C27B0;
      }

    }

    //Transitions

    .budge-right {
      visibility: visible;
      -webkit-animation: budgeRight 1s ease;
      animation: budgeRight 1s ease;
      -webkit-animation-iteration-count: 1;
      animation-iteration-count: 1;
    }

    .budge-left {
      visibility: visible;
      -webkit-animation: budgeLeft 1s ease;
      animation: budgeLeft 1s ease;
      -webkit-animation-iteration-count: 1;
      animation-iteration-count: 1;
    }
  }

  //General class

  .hidden {
    visibility: hidden;
  }

  .visible {
    visibility: visible;
  }
}

//Media queries

@media screen and (max-width: 48rem) {
._body {
    .main-container {
      .next-container {

        width:100%;
        font-size: 1rem;

        .block {
          width: 100%;
          display:block;

          .middle {
            width: 100%;
          }
        }
      }
    }
  }
}

@media screen and (max-width: 30rem) {
._body {
  .main-container {
    #box-container {

      display: block;

        .side {
          width: 100%;
        }

        .center-side {
          background-color: #4FC3F7;
        }
      }
    }
  }
}

</style>
