<script setup lang="ts">
import Card from "./components/Card.vue";
import HeaderCard from "./components/Header.vue";
import { reactive } from "vue";

interface Pokemon {
  pokemons: any;
}

let state: Pokemon = reactive({
  pokemons: [],
});

const getPokemonsUrl = async (url: string) => {
  try {
    const response = await fetch(url);
    return response.json();
  } catch (error) {
    console.log(`error: ${error}`);
  }
};

const getPokemon = async () => {
  try {
    const pokemon = await fetch(
      "https://pokeapi.co/api/v2/pokemon?limit=48&offset=0"
    );
    const poke = await pokemon.json();
    const promises = await poke.results.map(async (pokemon: { url: any }) => {
      return await getPokemonsUrl(pokemon.url);
    });
    const result = await Promise.all(promises);
    state.pokemons = result;
    console.log(state.pokemons);
    return state.pokemons;
  } catch (error) {
    console.log(`erro: ${error}`);
  }
};
getPokemon();
</script>

<template>
  <div class="body">
    <HeaderCard />
    <div class="container">
      <ul class="list">
        <li v-for="pokemon in state.pokemons" :key="pokemon.name">
          <Card
            :name="pokemon.name"
            :url="pokemon.sprites.front_default"
            :id="pokemon.id"
            :pokemonTypes="pokemon.types"
            :bg="pokemon.types[0].type.name"
          />
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.body {
  max-width: 100%;
  height: 100%;
}
.container {
  max-width: 100%;
  height: 100%;
  padding: 1rem;
}

.list {
  list-style: none;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 1rem;
}
</style>
