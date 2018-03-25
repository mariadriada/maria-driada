<template>
  <li class="skill-item">
    <figure >
      <a target="_blank" :href="`${ doc }`">
        <img :src="`${ img }`" :alt="`${ alt }`" />
      </a>
    </figure>
    <hgroup class="name">
      <h1 class="name-text"> {{ name }} </h1>
      <h2 class="level-tag"> {{ tag }} </h2>
      <h3 class="description"> {{ description }} </h3>
    </hgroup>
  </li>
</template>

<script>
export default {
  props: ['name', 'description', 'level', 'img', 'alt', 'doc',  'tag']
}
</script>

<style lang="scss">
.skill-item {
  min-width: 23%;
  max-width: 23%;
  //height: 16em;
  max-height: 16em;
  display: flex;
  align-items: baseline;
  flex-direction: column;
  align-items: center;
  margin: .5em;
  padding: .5em;

  figure {
    width:100%;
    height:40%;
    padding: .5em 0 0 0;

    img {
      //width: auto;
      min-width:5rem;
      height: 100%;
      display: block;
      margin: 0 auto;
      border: 0px;
    }
  }

  hgroup {
    width:100%;
    height:40%;
    text-align:center;
    font-size: 1rem;
    //font-family: 'Orbitron', sans-serif;    font-family: 'Roboto Mono', monospace;

    h1{
      padding: .5em;
      color: #01579B;
      font-size: 1.5em;
      font-weight: 400;
      font-family: 'Roboto Mono', monospace;
    }

    h2 {
      padding: .5em;
      font-weight: 400;
      color: #F9FBE7;
      font-size: 1.1em;
      font-family: 'Ubuntu', sans-serif;
    }

    h3 {
      padding: 0 .5em 0.5em .5em;
      font-weight: 400;
      font-size: 1em;
      text-align: justify;
      font-style: Italic;
      padding: .5em;
      color: #757575;
    }
  }

  // Style performance //mixin
  @mixin performance($bkg, $border-color, $text-color, $content) {

    background-color: $bkg;
    box-shadow: 0 1px 7px $border-color;

    *.name>.level-tag {

      background-color: $border-color;

      &:after {
        content: $content;
      }
    }

    *.name>.name-text {
      color: $text-color
    }
  }

  // High peformance
  &.high {
    @include performance(#E8F5E9, #4CAF50, #1B5E20,'Hihg applied performance');
  }

  // Moderate performance
  &.moderate {
    @include performance(#FFF8E1, #FFA726, #E65100, 'Moderate applied performance');
  }
}

@media screen and (max-width: 48rem) {
    .skill-item {
      min-width: 40%;
      background-color: red;
     // font-size: .5rem;
      max-height: 18rem;

      figure {
        img {
          max-width:8rem;
        }
      }
    }
  }

  @media screen and (max-width: 30rem) {
    .skill-item {
      min-width: 80%;
      max-height: 16rem;

    }
  }
</style>
