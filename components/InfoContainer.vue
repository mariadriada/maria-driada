<template>
  <div class="info-container">

    <figure v-if="img">
          <img :src="`${ img }`" :alt="`${ alt }`" />
    </figure>

    <list :idData="`${ idData }`" v-if="activeList">
    </list>

  </div>
</template>

<script>

import List from '~/components/TextList.vue'

export default{
  components: {
    List
  },
  props: ['img','alt','activeList', 'idData'],
 }

</script>

<style lang="scss">

.info-container{
  width: 100%;
  height: 67vh;
  display: flex;
  display: -ms-flex;
  display: -webkit-flex;
  display: -moz-flex;
  justify-content: center;
  -webkit-justify-content: center;
  align-items: center;
  -webkit-align-items:center;
  position: relative;


  figure{
    height: inherit;
    margin-left: 40%;

    img{
      height: inherit;
    }
  }

  // Performance professional list
  &.data2 {
    height: inherit;

    .text-list>ul>li>.line-text {
      color: #03A9F4;
      padding: 0 0 1.3em 2em;

      .text {
        font-size: 1.4em;
        font-style: normal;
        text-align: left;
      }
    }
  }

}

//Media queries

@media screen and  (max-width: 48rem) {

  .info-container {

    height: 60vh;

    figure {
       margin-left: 0%;
    }

    // Performance professional list
    &.data2 {

    .text-list>ul {

      padding-bottom: .5em;

        li {
          .line-text {
            z-index:5;
            font-size: .7rem;
          }
        }
      }

    }
  }

}

// Media query

@media screen and (max-width: 30rem) {
  .info-container {
    height: 35vh;
  }
}

</style>
