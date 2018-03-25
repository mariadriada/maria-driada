<template>
  <div id="main-container">

    <banner class="header2-container""></banner>

    <div id="data-container">

      <nav>
        <skills-menu/>
      </nav>

      <div class="dinamic-text">

        <div class="active panel maintext">
           <opacity-container :text="`${ maintext }`" class="normal center">
            </opacity-container>
        </div>

        <skills class=" panel"></skills>
        <experience class="panel"></experience>
        <!--<resume class="panel"></resume>-->

        <!-- Summary -->
        <redirect class="panel"
          :title ="`${ summary.title }`"
          :description ="`${ summary.description }`"
          :link ="`${ summary.link }`"
          :textlink ="`${ summary.textlink }`"
          >
        </redirect>
        <!-- /Summary -->

        <!-- Code -->
        <redirect class="panel"
          :title ="`${ code.title }`"
          :description ="`${ code.description }`"
          :link ="`${ code.link }`"
          :textlink ="`${ code.textlink }`"
          >
        </redirect>
        <!-- /Code -->

        <code class="panel"></code>
        <contact class="panel"></contact>

      </div>
    </div>
  </div>
</template>

<script>

import Banner from '~/components/Banner2.vue'
import Skills from '~/components/Skills.vue'
import Experience from '~/components/Experience.vue'
import Contact from '~/components/Contact.vue'
import Redirect from '~/components/Redirect.vue'
import OpacityContainer from '~/components/OpacityContainer.vue'
import SkillsMenu from '~/components/menu/Menu.vue'



export default {

  components: {
    Banner,
    Skills,
    Experience,
    Contact,
    Redirect,
    OpacityContainer,
    SkillsMenu
  },
  data () {
    return {
      maintext:  `I love everything about software and I know that it´s a big world.
                    For that, I focus on receive the client's needs and propouse alternatives solve their problems,
                    until they are satisfied; I don't know everything,
                    but I find the appropiate tecnology, asimilate and apply it.`,
      summary: {
        title: 'Summary',
        description: 'You can find my summary detail on',
        link: 'https://www.linkedin.com/in/mariadriada/?locale=en_US',
        textlink: 'LinkedIn'
      },
      code: {
        title: 'Repository',
        description: 'This project is developed on the Nuxt.js platform. And you can find the code on ',
        link: 'https://github.com/mariagiraldo/maria-driada',
        textlink: 'Github repository'
      }
    }
  }

}

</script>

<style lang="scss">

#main-container {

  background-color: #4FC3F7;
 // min-height: 100vh;
  position: relative;
  font-family: 'Ubuntu', sans-serif;

  #header2-container {
    #Skills-link {
      @include disable(#FFFF00);
    }
  }

  #data-container {
    min-height: 60vh;
    height: auto;
    max-height: auto;
    width: inherit;
    background-color:  red;
    position: relative;
    top: 29vh;
    z-index: 3;

    nav {
      width: 100%;
      height: auto;
     // position: fixed;
      z-index: 3;
    }

    .dinamic-text {

      @include flexbox;
      @include align-items(center);
      @include justify-content(center);

      width: 100%;
      height: auto;
      background-color: #FFF9C4;
      margin: 0 auto;
      position: relative;
      font-family: 'Ubuntu', sans-serif;
      border: 1px solid red;

      .panel {

        width:100%;
       // height:auto;
        position: absolute;
        left: -500%;
        //text-align: center;
        padding: 2em 0 2em 0;
        display: none;

        &.active {
          position: relative;
          left: 0;
          display:block;
        }
      }
    }
  }
}

//Media queries

@media screen and (max-width: 48rem) {
  #main-container {
  //  font-size: .5rem;

    #data-container {
      // background-color:red;
       top: 15vh;

    }
  }
}

@media screen and (max-width: 20rem) {
  #main-container {
  //  font-size: .5rem;

    #data-container {
       top: 85vh;

    }
  }
}

</style>
