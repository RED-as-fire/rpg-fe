<template>
  <v-app>
    <v-app-bar app dark color="amber darken-3">
      <div class="text-center">
        <v-row class="" color="amber darken-3">
        <v-btn
            class="mx-3"
            v-on:click="toggle='character-viewer'"
            rounded
            color=" amber deep-orange darken-3"
            dark
        >
          Personaggi
        </v-btn>
        <v-btn
            class="mx-3"
            color=" amber deep-orange darken-3"
            v-on:click="toggle='character-creator'"
            rounded
            dark
        >
          Crea!
        </v-btn>
        </v-row>
      </div>
    </v-app-bar>

    <v-main>
      <CharacterViewer v-show="toggle==='character-viewer'" />
      <CharacterCreator v-show="toggle==='character-creator'" />
    </v-main>

  </v-app>
</template>

<script>
import CharacterViewer from './components/CharacterViewer.vue'
import CharacterCreator from './components/CharacterCreator.vue'

export default {
  name: 'App',

  components: {
    CharacterCreator,
    CharacterViewer,
  },

  data: function () {
    return {
      toggle: "character-viewer"
    }
  }
};
</script>
