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
          class="d-inline-flex pa-2"
          elevation="2"
          outlined
          shaped
      >
        <div>
          <label for="character-name">Character Name: </label>
          <input type="text" id="character-name" v-model="name" placeholder="Enter a name" /> <br /><br />
          <label for="professions-list">Character Profession: </label>
          <select id="professions-list" v-model="profession">
            <option value="Mage">Mage</option>
            <option value="Thief">Thief</option>
            <option value="Warrior">Warrior</option>
          </select>
          <p>{{name}}</p>
          <p>{{profession}}</p>
        </div>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'CharacterCreator',
}
</script>
