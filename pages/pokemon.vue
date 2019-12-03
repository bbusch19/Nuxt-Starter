<template>
  <fragment>
    <input v-model="pokemonName" type="text" />
    <button @click="getPokemon">Get Pokemon!</button>
    <div v-if="pokemon">{{ pokemon }}</div>
    <div v-if="errorOcurred">Oops! Something went wront wit your request</div>
  </fragment>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      pokemonName: null,
      pokemon: null,
      errorOcurred: false
    }
  },
  methods: {
    async getPokemon() {
      try {
        this.errorOcurred = false
        const data = await axios.get(
          `https://pokeapi.co/api/v2/pokemon/${this.pokemonName}`
        )
        this.pokemon = data
      } catch (error) {
        this.pokemon = null
        this.errorOcurred = true
      }
    }
  }
}
</script>
