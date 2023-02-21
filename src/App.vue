<template>
  <div>
    <h1>List of Pokemon</h1>
    <button @click="ch()">get url</button>
    <ol>
      <li v-for="pokemon in pokemons" :key="pokemon.name">
        {{ pokemon.name }}
        <ol><li>
        {{pokemon.url}}
      </li>
      </ol>
      </li>
    </ol>
  </div>
</template>

<script>
const api = "https://pokeapi.co/api/v2/pokemon"
const api1 = api + "/1"
export default {
  data() {
    return {
      urls: [],
      pokemons: []
    };
  },
  mounted() {
    // Make an API request to get the data
    fetch(api + "?offset=0&limit=1300")
      .then(response => response.json())
      .then(data => {
        this.pokemons = data.results;
        var xy = this.pokemons[0];
        console.log(xy.url)
      })
      .catch(error => console.error(error));
  },
  methods: {
    ch() {
      fetch(api1)
      .then(response => response.json())
      .then(data => {
        this.urls = data.results
        console.log(urls)
      })
    }
  }
};
</script>
