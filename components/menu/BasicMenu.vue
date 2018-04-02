<template>
    <ul id="basic-menu">
      <li v-for="{ id, name, to } in links" :id="`${ name }-link`" :class="`${ name }-link`">
        <nuxt-link :to ="`${ to }`">
          {{ name }}
        </nuxt-link>
      </li>
    </ul>
</template>

<script>

export default {
  data () {
    return {
      links: [
        { id: 1, name: 'About', to: '/about' },
        { id: 2, name: 'Skills', to: '/skills' },
        { id: 3, name: 'Experience', to: '/experiene' },
      ]
    }
  }
}

</script>


<style lang="scss">

#basic-menu {

  @include flexbox;
  @include align-items(center);
  @include justify-content(flex-end);

  width: inherit;
  height: inherit;

  list-style: none;
  padding: 0;
  margin: 0;

  li {
    padding: .5em 0 .5em 1em;
    font-size: 1.3em;

    a {
      text-decoration: none;
      color: #9C27B0;

      transition:  color 0.8s linear 0.2s;
      -webkit-transition:color 0.8s linear 0.2s;

      &:hover {
        @include active(#4FC3F7);
      }
    }
  }
}

</style>
