<template>
  
</template>

<script>
import axios from 'axios'

const api = "https://pokeapi.co/api/v2/pokemon?limit=151"

export default{
  data(){
    return {
      pokemons: [],
      urls: [],
    }
  },
  methods: {
    fetchPoke(){
      axios.get(api)
      .then((allPoke) =>{
        allPoke.results.forEach((allPoke) =>{
          PokeData(pokemon)
        })
      })
    },
    PokeData(pokemon){
      let url = pokemon.url

      axios.get(url)
      .then((pokeData) => {
        renderPoke(pokeData)
      })
    },
    renderPoke(pokeData){
      pokeName = pokeData.name
      pokeId = pokeData.id
      pokeImage(pokeId)
    },
    pokeImage(pokeId) {
      pokeSrc = `https://unpkg.com/pokeapi-sprites@2.0.2/sprites/pokemon/other/dream-world/${pokeID}.svg`
    }
  }
}

</script>
