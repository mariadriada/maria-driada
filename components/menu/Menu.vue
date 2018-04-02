<template>
  <ul class="menu">
    <opt v-for="{ id, name, window, active, link } in options " @move="move"
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
        { id: 1, name: 'Performance', window:'', active: true, link: '' },
        { id: 2, name: 'Technologies', window:'', active: true, link: '' },
        { id: 3, name: 'DataBases', window:'', active: true, link: ''},
      ]
    }
  },
  methods: {
    move() {
      this.$emit('move')
    }
  },
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
  background-color: #FFFDE7;
  padding: 0;

}

</style>
