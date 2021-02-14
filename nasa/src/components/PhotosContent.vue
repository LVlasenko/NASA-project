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
    <button  v-show="items.length" class="btn-load" @click="addPhoto">Show More</button>
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
          this.items.push(photos);
          console.log(photos, 'photos');
          this.$forceUpdate();
        }catch (e) {
          console.log(e)
        }
      }
    },
    addPhoto() {
      console.log('click');
      this.photosNumber+=2;
      console.log(this.photosNumber);
    }
  }
}
</script>

<style >
.container {
  position: absolute;
  top: 0;
  right: 0;
  width: 50%;
  background-color: beige;
  display: flex;
  flex-direction: column;
}

.btn-load{
  position: absolute;
  left: 50%;
  transform: translate(-50%);
  bottom: 0;
}
.photoItem {
  width: 50%;
  transition: 0.8s ease;
  box-shadow: 5px 5px 10px 2px #cccccc;
}
.photoItem img {
  width: 100%;
}
</style>