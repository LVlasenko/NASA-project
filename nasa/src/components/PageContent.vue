<template>
  <main>
    <SelectSection />
    <PhotosContent />
  </main>
</template>

<script>
import SelectSection from './SelectSection.vue'
import PhotosContent from './PhotosContent.vue'

export default {
  name: 'PageContent',
  components: {
    SelectSection,
    PhotosContent
  }
}
</script>

<style lang="scss">
</style>