<template>
  <ul class="menu">
    <opt v-for="{ id, name, window, active, link } in options "
    :key = "id"
    :name = "`${ name }`"
    :window = "`${ window }`"
    :link = "`${ link }`"
    v-if = "active">
    </opt>
  </ul>
</template>

<script>
import Opt from '~/components/menu/option.vue'

export default {
  components: {
    Opt
  },
  data () {
    return {
      options: [
      //  { id: 1, name: 'About', window:'selft', active: true,  link: '/about' },
        { id: 2, name: 'Performance', window:'', active: true, link: '.' },
        { id: 3, name: 'Development', window:'', active: true, link: '.' },
        { id: 4, name: 'Data', window:'', active: true, link: ''},
      //  { id: 5, name: 'Code', window:'', active: true, link: 'https://github.com/mariagiraldo/maria-driada', active: true },
      //  { id: 6, name: 'Contact', window:'', active: true, active: true, link: '' }
      ]
    }
  }
}
</script>

<style lang="scss">

.menu {

  @include flexbox;
  @include align-items(flex-end);
  @include justify-content(center);

  width: 100%;
  height: 100%;
  list-style: none;
  font-family: 'Ubuntu', sans-serif;
  background-color: red;
  padding: 0;
 // margin-top: -3em;


}

//Media queries

@media screen and (max-width: 48rem) {
  .menu {
    //@include justify-content(center);
  }
}

</style>
