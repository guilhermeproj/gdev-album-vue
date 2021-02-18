<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <MainPage msg="Bem vindo ao projeto Album Interativo" />
    <div v-for="(album, index) in albums" :key="index">
      <!-- <MainPage :name="album.title" :userId="album.userId" :id="album.id" />
      {{ index + 1 }} {{ album.title }} -->
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import MainPage from "@/components/MainPage.vue";
// import Api from "@/service/api";

export default {
  name: "Home",
  components: {
    MainPage,
  },
  data() {
    return {
      albums: [],
    };
  },

  methods: {
  },
};

</script>
