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
          Crea il tuo personaggio!
        </h1>
      </v-col>
    </v-row>
    <v-row class="justify-center">
      <v-card
          class="d-inline-flex pa-2 justify-content-center"
          elevation="24"
          outlined
      >
        <div class="justify-center">
          <label for="character-name">Nome del personaggio: </label>
          <input type="text" id="character-name" v-model="name" placeholder="Inserisci un nome" /> <br /><br />
          <label for="professions-list">Classe del personaggio: </label>
          <select id="professions-list" v-model="profession">
            <option value="Mago">Mago</option>
            <option value="Ladro">Ladro</option>
            <option value="Guerriero">Guerriero</option>
            <option value="Paladino">Paladino</option>
            <option value="Chierico">Chierico</option>
          </select> <br/> <br />
          <label for="character-life">Vitalità: </label>
          <input type="text" id="character-life" v-model="life" placeholder="Inserisci un valore" /> <br /><br />
          <label for="character-res">Resistenza: </label>
          <input type="text" id="character-res" v-model="res" placeholder="Inserisci un valore" /> <br /><br />
          <label for="character-weapon">Arma di inizio: </label>
          <input type="text" id="character-weapon" v-model="weapon" placeholder="Inserisci un'arma" /> <br /><br />
          <v-btn v-on:click="postCharacter">Crea!</v-btn>
        </div>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
import axios from 'axios';

export default {
  name: 'CharacterCreator',
  data: function () {
    return {
      name: null,
      profession: null,
      life: null,
      res: null,
      weapon: null,
    }
  },
  methods: {
    postCharacter: function () {
      axios
          .post('http://localhost:3000/characters', {
            name: this.name,
            profession: this.profession,
            life: this.life,
            res: this.res,
            weapon: this.weapon
          });
    }
  }
}
</script>

<style>

</style>
