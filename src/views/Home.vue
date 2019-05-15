<template>
  <div class="home">
    <main id="nice">
      <div class="intro">
        <div>
          <h1>Welcome to the Dark Side</h1>
        </div>
        <div>
          <input type="text" name="text" id="text" v-model="nombre" placeholder="Tu nombre...">
          <button v-on:click="comprobar">Eres Tú?</button>
        </div>
      </div>

      <div v-if="cierto">
        <h2 class="centrar">{{felicitacion}}</h2>
        <h1 class="centrar">{{quiero}}</h1>
      </div>

      <!-- video de gandalf -->
      <div v-if="cierto == false">
        <iframe
          src="https://giphy.com/embed/YkfhemFXalh7O"
          width="390"
          height="200"
          frameborder="0"
          class="giphy-embed"
          allowfullscreen
        ></iframe>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nombre: "",
      cierto: null,
      felicitacion:
        "Feliz cumpleaños Ariën, Mixgupi, La Jinete Peste, La Alien de Gupilandia, La Hacedora de Porros, La Intumbable, la Rompedora de Penes y  Protectora de los Jinetes... mi amiga, mi cielo, mi mujer.",
      quiero: "Te quiero como solo la Eternidad sabe hacerlo."
    };
  },
  methods: {
    comprobar() {
      if (this.nombre === "Ariën") {
        this.cierto = true;
      } else {
        this.cierto = false;
      }
      console.log(this.cierto);
    }
  }
};
</script>

<style>
#nice {
  text-align: center;
  background-color: #2d0b0b;
  color: white;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0px;
  left: 0px;
  font-family: tolkien;
}
@font-face {
  font-family: "tolkien";
  src: url("Tolkien Regular.ttf");
}
.centrar {
  justify-content: center;
  padding: 1%;
  font-family: tolkien;
}
.intro {
  padding: 2%;
}
</style>
