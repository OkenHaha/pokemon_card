<template>
  <div>
    <h1>List of Pokemon</h1>
    <ul>
      <li v-for="pokemon in pokemons" :key="pokemon.name">
        {{ pokemon.name }}
      </li>
    </ul>
  </div>
</template>

<script>
  const api = "https://pokeapi.co/api/v2/pokemon"
export default {
  data() {
    return {
      pokemons: []
    };
  },
  mounted() {
    // Make an API request to get the data
    fetch(api + "?offset=10&limit=1300")
      .then(response => response.json())
      .then(data => {
        this.pokemons = data.results;
      })
      .catch(error => console.error(error));
  }
};
</script>
