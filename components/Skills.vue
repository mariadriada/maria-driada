<template>
  <article class="skills">
    <header><text-line :message="title"></text-line></header>
    <section><p> {{ description }} </p></section>
    <div class="skills-container">

      <ul class="skill-content">
        <skill-item v-for="{ id, name, description, level, img, alt, doc } in code "
        :key = "id"
        :name = "`${ name }`"
        :description = "`${ description }`"
        :img = "`${ img }`"
        :alt = "`${ alt }`"
        :level = "`${ level }`"
        :class = "`${ level }`"
        :doc = "`${ doc }`"
        >
        </skill-item>
      </ul>
    </div>
  </article>
</template>

<script>
import TextLine from '~/components/TextLine.vue'
import SkillItem from '~/components/SkillItem.vue'

export default {
  components: {
    TextLine,
    SkillItem
  },
  data () {
    return {
      title: 'My Skills',
      description: `I love everything about software and I know that it´s a big world.
                    For that, I focus on receive the client's needs and propouse alternatives solve their problems,
                    until they are satisfied; I don't know everything,
                    but I find the appropiate tecnology, asimilate and apply it.`,
      code: [
        { id:1, name:'HTML5', description: 'Html5 and old versions.', level: 'high', img: '/img/skills/html5.png', alt: 'HTML5', doc:'https://html.spec.whatwg.org/dev/' },
        { id:2, name:'CSS3', description: 'CSS3 and old versions.', level: 'high', img: '/img/skills/css3.png', alt: 'CSS3', doc:'https://www.w3.org/Style/CSS/' },
        { id:3, name:'Sass', description: 'Scss syntax, LiveReload and prepros tools.', level: 'high', img: '/img/skills/sass.png', alt: 'Sass', doc:'https://sass-lang.com/' },
        { id:4, name:'Less', description: 'I like more Sass.', level: 'moderate', img: '/img/skills/less.png', alt: 'Less', doc:'http://lesscss.org/' },
        { id:5, name:'ECMAScript-2015', description: 'Vanilla Js skills.', level: 'high', img: '/img/skills/javascript.png', alt: 'Javascript', doc:'http://www.ecma-international.org/ecma-262/6.0/' },
        { id:6, name:'ECMAScript-2016', description: 'Vanilla Js skills.', level: 'high', img: '/img/skills/es6.png', alt: 'ECMAScript6', doc:'http://www.ecma-international.org/ecma-262/7.0/' },
        { id:7, name:'JQuery', description: 'I like more Vanilla JS.', level: 'high', img: '/img/skills/jquery.png', alt: 'JQuery', doc:'http://www.ecma-international.org/ecma-262/7.0/' },
        { id:8, name:'Angular', description: 'Angular and AngularJs.', level: 'moderate', img: '/img/skills/angular.png', alt: 'Angular', doc:'https://angular.io/' },
        { id:9, name:'TypeScript', description: '', level: 'moderate', img: '/img/skills/typescript.png', alt: 'TypeScript', doc:'https://www.typescriptlang.org/' },
        { id:10, name:'VUE.JS', description: '', level: 'high', img: '/img/skills/vue.png', alt: 'Vue Js', doc:'https://vuejs.org/' },
        { id:11, name:'NUXT', description: '', level: 'high', img: '/img/skills/nuxt.png', alt: 'Nuxt Js', doc:'https://nuxtjs.org/' },
        { id:12, name:'NodeJs', description: 'Wonderful world to discover!', level: 'moderate', img: '/img/skills/nodejs.png', alt: 'NodeJs', doc:'https://nodejs.org/en/' },
        { id:13, name:'Webpack', description: 'Also Gulp.js skills.', level: 'moderate', img: '/img/skills/webpack.png', alt: 'Webpack', doc:'https://webpack.js.org/' },
        { id:13, name:'Django', description: 'Python skills.', level: 'moderate', img: '/img/skills/django.png', alt: 'Django', doc:'https://www.djangoproject.com/' },
        { id:13, name:'C and C++', description: 'Low level  programing skills.', level: 'high', img: '/img/skills/cpp.png', alt: 'C and C++', doc:'https://isocpp.org/std/the-standard' },
        { id:13, name:'Oracle', description: 'Oracle database.', level: 'moderate', img: '/img/skills/oracle.png', alt: 'Oracle database', doc:'https://docs.oracle.com/en/database/' },
        { id:13, name:'MySql', description: 'Oracle Msql database.', level: 'high', img: '/img/skills/mysql.png', alt: 'MySql', doc:'https://www.mysql.com/' },
        { id:13, name:'Sql Server', description: 'Dinamic SQL and transact Sql skills.', level: 'high', img: '/img/skills/sqlserver.png', alt: 'MySql', doc:'https://www.mysql.com/' },
        { id:13, name:'PostgreSql', description: 'Databases migration skills.', level: 'moderate', img: '/img/skills/postgresql.png', alt: 'MySql', doc:'https://www.mysql.com/' },
        { id:13, name:'SqLite', description: 'Embedded database skills.', level: 'high', img: '/img/skills/sqlite.png', alt: 'SqLite', doc:'https://www.postgresql.org/' },

      ]

    }
  }
}

</script>

<style lang="scss">
.skills {
  font-size: 1rem;
  p {
      text-align: justify;
      font-size: 1.3em;
      padding: 1em 0 0 0;
      color: #616161;
  }
  .skills-container {
    width: 100%;

    .skill-content {
      width: inherit;
      font-size: 1rem;
      list-style: none;
      padding-left: 0;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
  }
}
</style>
