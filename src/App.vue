<template>
  <v-app>
    <v-row>
      <v-col>
        <v-btn class="view"
            v-on:click="toggle='character-viewer' ; getCharacters()"
            color="amber lighten-4"
            elevation="24"
            fab
            x-large
        >
          <v-icon>mdi-script-text-outline</v-icon>
        </v-btn>
        <v-btn class="crea"
            v-on:click="toggle='character-creator'"
            color="amber lighten-4"
            elevation="24"
            fab
            x-large
        >
          <v-icon>mdi-sword-cross</v-icon>
        </v-btn>
        <v-btn class="link"
               v-on:click="openLink()"
               color="amber lighten-4"
               elevation="24"
               fab
               x-large
        >
          <v-icon>mdi-sack</v-icon>
        </v-btn>
      </v-col>
    </v-row>
    <v-main class="main">
      <CharacterViewer v-show="toggle==='character-viewer'" :characters = "characters" />
      <CharacterCreator v-show="toggle==='character-creator'" />
    </v-main>
  </v-app>
</template>

<script>
import CharacterViewer from './components/CharacterViewer.vue'
import CharacterCreator from './components/CharacterCreator.vue'
import axios from "axios"

export default {
  name: 'App',
  components: {
    CharacterViewer,
    CharacterCreator
  },
  data: function () {
    return {
      toggle: "character-viewer",
      characters: null
    }
  },
  methods: {
    getCharacters: function () {
      axios
          .get('http://localhost:3000/characters')
          .then(response => (this.characters = response.data))
    },
    openLink: function () {
      window.open("https://dungeonsanddragons.fandom.com/it/wiki/D%26D_5e_italiano_Wiki", "_blank");
    }
  },
  mounted: function () {
    this.getCharacters();
  }
}
</script>

<style>
div[data-app='true'] {
  background: url('assets/back.jpg') no-repeat center center fixed !important;
  background-size: cover;
}
.view {
  position: absolute;
  top: 150px;
  left: 100px;
}

.crea{
  position: absolute;
  top: 50px;
  left: 200px;
}

.link{
  position: absolute;
  top: 630px;
  left: 100px;
}

</style>
