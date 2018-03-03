<template>
  <div class="line-text">

    <div class="circle"></div>
    <div class="text"><span> {{ text }} </span></div>
  </div>
</template>

<script>
export default{
  props: ['text', 'circle']
}
</script>

<style lang="scss">
$color:#FFFDE7;;

.line-text {
  font-size: 1rem;
  width: 100%;
  display: flex;
  display: -ms-flexbox;
  align-items:center;
  -ms-flex-align:center;
  font-size: 1rem;
  line-height: 1.5em;
  min-height: 1.5em;
  height: 1.5em;
  color: $color;
  //padding-top: 1em;
  //border: 1px solid blue;
  margin-bottom: 1.3em;


  .text {
    width: 90%;
    //text-align: right;
    text-align: left;
    //padding-right: 0.3em;
    padding-left: 0.3em;
    font-size: 2em;
    line-height: 2em;
    margin: -0.1em 0 0 0;
  }

  .circle {
    width: 1.5em;
    height: 1.5em;
    background-color: $color;
    border-radius: 50%;
    opacity: 0.5;
    line-height: 1.5em;
  }
}


@media  (max-width: 48rem ) {
  .line-text {
     font-size: .7rem;
  }
}
@media  (max-width: 30rem) {
  .line-text {
     font-size: .6rem;
  }
}
@media  (max-width: 20rem) {
  .line-text {
     font-size: .5rem;
  }
}

</style>
