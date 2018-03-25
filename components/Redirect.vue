<template>
  <article>
     <header>
      <text-line :message="`${ title }`"></text-line>
      </header>
      <section>
        <p> {{ description }}
        <a target="_blank" :href="`${ link }`"> {{ textlink }} </a>
      </p>
      </section>
  </article>
</template>

<script>
import TextLine from '~/components/TextLine.vue'

export default {
  components: {
    TextLine
  },
  props: ['title', 'description', 'link', 'textlink']

}
</script>

<style>
</style>
