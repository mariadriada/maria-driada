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
        { id: 1, name: 'About', window:'selft', active: true,  link: '/about' },
        { id: 2, name: 'Skills', window:'new', active: true, link: '.' },
        { id: 3, name: 'Experience', window:'new', active: true, link: '.' },
        { id: 4, name: 'Resume', window:'new', active: true, link: 'https://www.linkedin.com/in/mariadriada/?locale=en_US'},
        { id: 5, name: 'Code', window:'new', active: true, link: 'https://github.com/mariagiraldo/maria-driada', active: true },
        { id: 6, name: 'Contact', window:'new', active: true, active: true, link: '' }
      ]
    }
  }
}
</script>

<style lang="scss">
.menu {
  width: inherit;
  height: 100%;
  list-style: none;
  padding: 0 3rem 0 0;
  display: flex;
  align-items: flex-end;
  justify-content: flex-end;
}
</style>
