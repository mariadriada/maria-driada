<template>
  <div class="text-list">
    <ul>
      <li v-for="{id, text, active, circle} in text " :key="id">
        <item :text="`${ text }`" :circle="`${ circle }`">>
        </item>
      </li>
    </ul>
  </div>
</template>

<script>

import Item from '~/components/Item.vue'

export default{

  components: {
    Item
  },
  props: ['idData'],
  data () {
    return {
      text: []
    }
  },
  methods: {
    updateData: function() {
      console.log('datosaca')
    }
  },
  beforeMount () {
    let list = [];
    if (this.idData === "1") {
      // Self description list
      list=
      [
        { id: 1, text: 'Self-taught and creative.', active: true, circle: true },
        { id: 2, text: 'Believe in teamwork.', active: true, circle: true },
        { id: 3, text: 'Know new technologies.', active: true, circle: true },
        { id: 4, text: 'love the methodology.', active: true, circle: true },
        { id: 5, text: 'Focus on improving.', active: true, circle: true },
        { id: 6, text: 'love nature.', active: true, circle: true },
        { id: 7, text: 'I am an enterprising woman.', active: true, circle: true },
      ]
    }
    else if (this.idData === "2") {
      // Performance professional list
      list=
      [
        { id: 1, text: 'Computer Tecnhology.', active: true, circle: '' },
        { id: 2, text: 'Computer Enginner Student, semester eighth.' , circle: '' },
        { id: 3, text: 'Analyst and software developer performance.', active: true, circle: '' },
      ]
    }
    this.text = list;
  }

}

</script>

<style lang="scss">

.text-list {
  width: 100%;

  ul {
    list-style: none;
    padding-left: 0;
    height: auto;
    font-style: italic;
    font-weight: 400;
  }

}

</style>
