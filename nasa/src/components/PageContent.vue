<template>
  <div>
    <Header msg="Nasa expeditions to MARS"/>
    <SelectSection />
    <PhotoSection />
  </div>
</template>

<script>
import Header from './Header.vue'
import SelectSection from './SelectSection.vue'
import PhotoSection from './PhotoSection.vue'

export default {
  name: 'PageContent',
  components: {
    Header,
    SelectSection,
    PhotoSection
  }
}
</script>

<style lang="scss">
</style>