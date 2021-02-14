<template>
<div class="photo">
  
</div>
</template>

<script>

export default {
  name: 'PhotoItem',
  props: {
      itemProps: true,
  },
  methods: {

  },
  beforeCreate() {
    this.$on('submitData', (value) => {
      let {selectedRover, selectedCamera, sol} = value
      this.getPhotos(selectedRover, selectedCamera, sol)
    })
  },
  created() {
    console.log(this.itemProps);
    t
  } 
  
}
</script>

<style scoped lang="scss">

</style>