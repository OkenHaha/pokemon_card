<template>
  <div>
    <h1>List of Pokemon</h1>
    <ol>
      <li v-for="pokemon in pokemons" :key="pokemon.name">
        {{ pokemon.name }}
        <ul>
          <li> {{pokemon.url}} </li>
        </ul>
        <br/>
      </li>
    </ol>
  </div>
</template>

<script>
import axios from 'axios'

const api = "https://pokeapi.co/api/v2/pokemon"
const api1 = api + "/1"
export default {
  data() {
    return {
      pokemons: []
    };
  },
  mounted() {
    axios.get(api + "?limit=2000&offset=0")
    .then(res => {
      this.pokemons = res.data.results
      console.log(this.pokemons[0].name)
    })
    
  }
};
</script>



<!-- axios.get(api)
    .then(res)
    .then(data => {
      this.pokemons = data.results
    })
    .catch(err => console.error(err) -->)
