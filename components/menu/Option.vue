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

      tabs.map(tab => tab.classList.remove('active'))
      tabs[i].classList.add('active')

      panels.map(panel => panel.classList.remove('active'))
      panels[i].classList.add('active')

      //Redirection validation
      if (this.link === '.')
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
      }
    }
  }
}
</script>

<style lang="scss">
.tabs-item {
  //background-color: #FAFAFA;
  margin-left: 1px;
  padding: 0.5em;
  color:#FAFAFA;
  min-width: auto;
  width: 6em;
  max-width: auto;
  text-align: center;
  font-size: 1.3em;
  border-radius: 0.5em 0.5em 0 0;
  cursor: pointer;

  &:hover {
    color: #FFFF00;
    font-weight: 500;
  }

  &.active {
    color: #FFFF00;
    font-weight: 500;
    transition:  0.3s;
    -webkit-transition: 0.3s;
  }
}
</style>
