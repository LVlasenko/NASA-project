<template>
<section class="photo-section">
  <PhotoItem />
</section>
</template>

<script>
import PhotoItem from './PhotoItem.vue'
export default {
  name: 'PhotoSection',
  data() {
    return {
      items: []
    }
  },
  components: {
    PhotoItem
  },
  methods: {

  },
  async created() {
    console.log('created');
  }

  
}
</script>

<style scoped lang="scss">
.photo-section {
    width: 100%;
    height: 650px;
}

</style>