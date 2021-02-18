<template>
  <div class="photos">
    <h1>This is an photo page</h1>
      <div v-for="(photo, index) in photos" :key="index"> 
      {{ index + 1 }} | {{ photo.id }} | 
       {{ photo.albumId }} 
      {{ photo.url}}
       {{ photo.id }}  -->
    <div class="card">
      <div class="card-image">
      <figure>
        <img src="currentImg" alt="Placeholder image">
      </figure>
      </div>  
    </div>
    <div><button class="button is medium is fullwidth">teste</button></div>
    </div> 
    <router-view />
  </div>
</template>
<script>
import Api from "@/service/api";
export default {
  name: "Photos",
  components: {},
  data() {
    return {
      isPhoto: true,
      currentImg: '',
      photos: {
        url: '',
        albumId: '',
        id: '',
      }
    };
  },
  mounted() {
    Api()
      .get(`/photos`)
      .then((photos) => {
        this.photos = photos.data;
        this.currentImg = this.photos.isPhoto;
        console.log("Fotos carregadas");
      });
  },
  methods: {
    loadPhoto: function(){
      if(this.isPhoto){
        this.isPhoto = false;
        this.currentImg = this.photos.url;
      }
    }
  }
}
</script>
