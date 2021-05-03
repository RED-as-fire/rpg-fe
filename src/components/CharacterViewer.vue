<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.png')"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          Visualizza i tuoi personaggi
        </h1>
        <p v-for="(character, index) in characters" v-bind:key="index">{{character.name}} è un {{character.profession}}, con {{character.life}} di vita, e {{character.res}} di resistenza. La sua arma iniziale è {{character.weapon}} !</p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>

export default {
  name: 'CharacterViewer',
  props: {
    characters: Array
  }
}
</script>
