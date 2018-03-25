<template>
  <section>
    Contact section
  </section>
</template>

<script>
export default {
  beforeMount () {
    console.log('before', this.$el);
   // let page = get "https://docs.google.com/forms/d/e/1FAIpQLSdBAU44bvfmagFyjiymfZSnaTd8sp5rmGLhAu4dOl0nzDPHtw/viewform?embedded=true"
   // this.$el.insertBefore("hola", this.$el)

    let xhttp = new XMLHttpRequest();
    xhttp.onreadystatechange = function() {
        if (this.readyState == 4 && this.status == 200) {
          // Typical action to be performed when the document is ready:
          this.$el.innerHTML = xhttp.responseText;
        }
    }
    xhttp.open("GET", "https://es.stackoverflow.com/questions/9209/agregar-un-html-completo-a-un-div", true);
    xhttp.send();

  //  this.$el.innerHTML = "<h1>holaaaaaaa</h1>";

  }
}
</script>

<style>
</style>
