<template>
  <div>
    <p>teste 1 2 3 4</p>
    <div v-for="(album, index) in albums" :key="index">
      {{ index + 1 }} | {{ album.title }} | {{ album.userId }}
    </div>
    <router-view />
  </div>
</template>

<script>
import Api from "@/service/api";
export default {
  name: "Album",
  components: {},
  data() {
    return {
      albums: [],
      // Api().get("/albums"),
    };
  },
  mounted() {
    
    console.log(this.$route.params)
    Api()
      .get("/albums")
      .then((albums) => {
        this.albums = albums.data;
        console.log("Album carregado");
      });
  },
};
</script>

<style lang="scss" scoped></style>
