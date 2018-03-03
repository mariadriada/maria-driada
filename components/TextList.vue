<template>
  <div class="text-list">
    <ul>
      <li v-for="{id, text, active, circle} in text " :key="id">
        <item :text="`${ text }`">
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
    if (this.idData === "1") {
      let list=
      [
        { id: 1, text: 'Self-taught and creative.', active: true, circle: true },
        { id: 2, text: 'I believe in teamwork.', active: true, circle: true },
        { id: 3, text: 'I like to know new technologies.', active: true, circle: true },
        { id: 4, text: 'I love the methodology.', active: true, circle: true },
        { id: 5, text: 'I focus on improving.', active: true, circle: true },
        { id: 6, text: 'I love nature.', active: true, circle: true },
        { id: 7, text: 'I am an enterprising woman.', active: true, circle: true },
      ]
      this.text = list;
    }
    else {
      let list=
      [
        { id: 1, text: 'frase 0', active: true, circle: true },
        { id: 2, text: 'frase 9', active: true, circle: true },
      ]
      this.text = list;
    }
  }

}
</script>

<style lang="scss">
.text-list {
  width: 100%;
  margin-left: 10%;

  ul {
    list-style: none;
    padding-left: 0;
    height: auto;
    font-style: italic;
    font-weight: 400;
  }
}

@media screen and (max-width: 48rem) {
  .text-list {
    //background-color: red;
    margin-left: 0%;
  }
}

</style>
