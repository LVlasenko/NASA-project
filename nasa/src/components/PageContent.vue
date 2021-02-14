<template>
  <div>
    <Header msg="Nasa expeditions to MARS"/>
    <SelectSection />
  </div>
</template>

<script>
import Header from './Header.vue'
import SelectSection from './SelectSection.vue'

export default {
  name: 'PageContent',
  components: {
    Header,
    SelectSection
  }
}
</script>

<style lang="scss">
</style>