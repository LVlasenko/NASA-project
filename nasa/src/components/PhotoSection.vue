<template>
<section class="photo-section">
  <PhotoItem 
      v-for="item in items"
      :itemProps="item"
      :key="item.id"
  />
</section>
</template>

<script>
import PhotoItem from './PhotoItem.vue'
export default {
  name: 'PhotoSection',
  data() {
    return {
      items: [],
    }
  },
  components: {
    PhotoItem
  },
  methods: {

  },
  async created() {
    console.log('created');
    try {
      const items = await (await fetch("https://api.nasa.gov/planetary/apod?api_key=KAbsfyUAS6Lx5NgC0rnVMeQv1xKuCldwFQtjTRr1"));
      this.items = items;
    } catch(e) {
      console.log(e, 'oops');
    }
  } 
  
}
</script>

<style scoped lang="scss">
.photo-section {
    width: 100%;
    height: 650px;
}

</style>