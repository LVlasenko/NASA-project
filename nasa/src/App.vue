<template>
  <div id="app">
    <PageContent />
  </div>
</template>

<script>
import PageContent from './components/PageContent.vue'

export default {
  name: 'App',
  components: {
    PageContent
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
