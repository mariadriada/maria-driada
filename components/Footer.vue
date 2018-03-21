<template>
  <footer>

    <section class="author">
      <p class="text">
        {{ text }}
      </p>
      <p class="cc"> {{ cc }} </p>
    </section>

    <aside class="img">
      <figure>
        <img :src="`${ img }`" :alt="`${ alt }`" />
      </figure>
    </aside>

  </footer>
</template>

<script>

export default {

  data () {
    return {
      text:'Design and development by',
      cc: '©MariaDriada',
      img: '/img/firma.png',
      alt: 'Maria Eugenia Giraldo Forero'
    }
  }

}

</script>


<style lang="scss">

footer {
  background-color: #FFEB3B;
  min-height: 25vh;
  width:100%;
  margin: 0 auto;
  display: flex;
  display: -ms-flex;
  display: -webkit-flex;
  font-size: 1rem;

  .author {

    width:50%;
    font-family: 'Indie Flower', cursive;
    font-size: inherit;
    display: flex;
    display: -ms-flex;
    display: -webkit-flex;
    display: -moz-flex;
    align-items: left;
    flex-direction: column;
    -ms-flex-direction: column;
    -webkit-flex-direction: column;
    -moz-flex-direction: column;
    justify-content: center;
    -ms-justify-content: center;
    -webkit-justify-content: center;
    -moz-justify-content: center;
    padding-left: 2em;
    color: #9C27B0;

    .text{
      padding-top: 1.5em;
      font-size: 1.3em;
    }

    .cc {
      font-size: 3.5em;
    }
  }

  .img {

    width: 50%;
    height:inherit;
    font-size:inherit;
    display: flex;
    display: -ms-flex;
    display: -webkit-flex;
    display: -moz-flex;
    justify-content: flex-end;
    -webkit-justify-content: flex-end;
    align-items: flex-end;
    -webkit-align-items: flex-end;
    padding-right: 2em;

    figure {
      width: 17em;
      border-top: 1px solid #9C27B0;;

      img {
        width: inherit;
        padding: .5em;
      }
    }

  }
}

//Media queries

@media screen and (max-width: 48rem) {
  footer {

    display: block;
    font-size: .7rem;

    .author {
      width: 100%;
      display:block;
      padding: 0;
      margin: 0 auto;
      text-align:center;
    }

    .img {
      width: 100%;
      padding: 1em 0 1em 0;

      figure{
        width: 100%;

        img {
          width: 40%;
          display:block;
          margin: 0 auto;
          padding-top:2em;
        }
      }
    }

  }
}

@media screen and (max-width: 38rem) {
  footer {
    .img {
      figure {
        img {
          width: 50%;
        }
      }
    }
  }
}


@media screen and (max-width: 28rem) {
  footer{
    .img {
      figure{
        img {
          width: 70%;
        }
      }
    }
  }
}

</style>
