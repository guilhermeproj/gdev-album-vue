<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Projeto desenvolvido com Vue.Js v2 seguindo a documentação oficial<br />
      podemos consulta-la através do seguinte link
      <a href="https://vuejs.org/v2/guide/" target="_blank" rel="noopener"
        >vue-guide introduction</a
      >.
    </p>
    <br />
    <button class="button is-success is-focused" @click="loadAlbum">
      Carregar Album
    </button>
    <button class="button is-success is-focused" @click="loadPhotos">Carregar Fotos</button>
    </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    msg: String,
  },
  methods: {
    loadAlbum: function() {
      // window.open("http://localhost:8080/album","_self");
      this.$router.push("Album");
      
    },
    loadPhotos: function(){
      // window.open("http://localhost:8080/photos","_self")
      this.$router.push("Photos")
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
