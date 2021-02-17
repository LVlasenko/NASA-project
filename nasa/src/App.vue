<template>
  <div id="app">
    <Header msg="Nasa expeditions to MARS"/>
    <PageContent />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import PageContent from './components/PageContent.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    PageContent,
    Footer
  }
}
</script>

<style lang="scss">
 * {
   box-sizing: border-box;
 }

 h1, h2, h3, h4, h5, h6, p, ul, ol, body {
    margin: 0;
    padding: 0;
}

</style>
