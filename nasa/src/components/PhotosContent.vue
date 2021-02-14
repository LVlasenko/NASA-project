<template>
  <div  class="container">
    <div v-for="item in items" :key="item.id">
      <div v-for="photos in item" :key="photos.id">
        <div v-for="(photo, index) in photos" :key="photo.id" class="photoItem">
              <img :src="photo.img_src"
                   v-if="index < photosNumber ">
        </div>
      </div>
    </div>
    <button  v-show="items.length" class="btn-load" @click="photosNumber+=2">Show More</button>
  </div>
</template>

<script>
import {event} from "@/main";
const axios = require("axios");

export default {
  name: "PhotosContent",
  beforeCreate() {
    console.log(event, 'event')
    event.$on('dataSubmit', (value) => {
      let {selectedRover, selectedCamera, sol} = value
      this.getPhotos(selectedRover, selectedCamera, sol)
    })
  },
  data() {
    return {
      items: [],
      url: "https://api.nasa.gov/mars-photos/api/v1/rovers/",
      api_key: "KAbsfyUAS6Lx5NgC0rnVMeQv1xKuCldwFQtjTRr1",
      photosNumber: 2
    };
  },
  methods: {
    async getPhotos(rover, camera, sol) {
      if(rover!==undefined|| camera!==undefined||sol!==undefined){
        try {
          const {
            data: photos
          } = await axios({
            url: `${this.url}${rover}/photos?sol=${sol}&camera=${camera}&api_key=${this.api_key}`,
          });
          this.items=[];
          this.photosNumber=2;
          this.items.push(photos);
          console.log(photos, 'photos');
        }catch (e) {
          console.log(e)
        }
      }
    }
  }
}
</script>

<style >
.btn-load{
  position: relative;
  left: 50%;
  transform: translate(-50%, 0);
  margin: 10px 0;
}
.item {
  margin: 0 auto;
  float: left;
  min-width: 0;
  margin: 2rem;
  transition: 0.8s ease;
  box-shadow: 5px 5px 10px 2px #cccccc;
}
.item img {
  width: 100%;
  max-width: 100%;
  height: auto;
}
</style>