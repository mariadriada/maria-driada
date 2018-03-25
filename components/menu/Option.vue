<template>
    <li @click="change" class="tabs-item" > {{ name }} </li>
</template>

<script>
export default {
  props: ['name', 'link', 'window'],
  methods: {
    change: function (e) {
      let tabs = Array.prototype.slice.apply(document.querySelectorAll('.tabs-item'))
      let panels = Array.prototype.slice.apply(document.querySelectorAll('.panel'))
      const i = tabs.indexOf(e.target);
      console.log(i);

      tabs.map(tab => tab.classList.remove('active'))
      tabs[i].classList.add('active')

      panels.map(panel => panel.classList.remove('active'))
      panels[i].classList.add('active')

      //Redirection validation
     /* if (this.link === '.')
      {
        console.log('activate container')
      }
      else {
        switch(this.window) {
          case 'selft':
              location.href = this.link
              break;
          case 'new':
              window.open(this.link)
              break;
          default:
              location.href = this.link
        }
      }*/

      if (this.window) {
        switch(this.window) {
          case 'selft':
              location.href = this.link
              break;
          case 'new':
              window.open(this.link)
              break;
          default:
              location.href = this.link
        }
      }
    }
  }
}
</script>

<style lang="scss">

.tabs-item {
  background-color: #FFF176;;
  padding: .5em 0 .5em 0;
  color:#FAFAFA;
  width: 35%;
  //width: 6em;
  max-width: auto;
  text-align: center;
  font-size: 1.1em;
  cursor: pointer;
//margin-left: 1px;

  transition:  color 0.8s linear 0.2s;
  -webkit-transition:color 0.8s linear 0.2s;

  &:hover {
    @include active();
  }

  &.active {
    @include active();
  }

}

//Media queries

@media screen and (max-width: 48rem) {
  .tabs-item {
   //padding: 5em 0 0 1em;
  }
}
</style>
