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
  justify-content: center;
  //border: 1px solid  red;
  align-items:center;
  -ms-flex-align: center;

  figure{
    height:inherit;
    margin-left: 60%;

    img{
      height: inherit;
    }
  }
}


@media screen and  (max-width: 48rem) {
  .info-container {
    height: 60vh;
    //background-color:red;
    figure {
       margin-left: 0%;
    }
  }
}

@media  (max-width: 30rem) {
  .info-container {
    height: 35vh;
  }
}


</style>
