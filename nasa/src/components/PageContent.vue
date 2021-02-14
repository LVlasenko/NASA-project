<template>
  <div>
    <Header msg="Nasa expeditions to MARS"/>
    <SelectSection />
    <PhotosContent />
  </div>
</template>

<script>
import Header from './Header.vue'
import SelectSection from './SelectSection.vue'
import PhotosContent from './PhotosContent.vue'

export default {
  name: 'PageContent',
  components: {
    Header,
    SelectSection,
    PhotosContent
  }
}
</script>

<style lang="scss">
</style>