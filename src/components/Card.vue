<script setup lang="ts">
const props = defineProps({
  name: { type: String, require: true },
  url: { type: String, require: true },
  id: { type: Number, require: true },
  pokemonTypes: { type: Array<any>, require: true },
  bg: { type: String, require: true },
  bgNumber: { type: String, require: true }
});

const pokemon =
  (props.id as number) < 650
    ? `src/asserts/animated/${props.id}.gif`
    : props.url;
</script>

<template>
  <div>
    <div class="card" :id="bg">
      <div class="card-image">
        <img :src="pokemon" alt="imagem do pokemon" />
      </div>
      <div class="card-body">
        <div class="card-top">
          <h3>{{ name?.toLocaleUpperCase() }}</h3>
          <div class="pokemonNumber" :id="bg">#{{ id }}</div>
        </div>

        <div className="card-bottom">
          <ul class="list">
            <li v-for="types in pokemonTypes" key="type.name" class="item">
              {{ types.type.name }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  max-width: 100%;
  max-height: 80px;
  height: 100%;
  padding: 13px;
  display: flex;
  align-items: center;
  border-radius: 8px;
  cursor: pointer;
}
.card-body {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card-image {
  padding: 10px 5px;
  margin-right: 10px;
  width: 100px;
}
.card-top {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 5px;
}

.pokemonNumber {
  padding: 4px 10px;
  border: 1px solid #F2F2F2;
  border-radius: 1rem;
  box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.514);
}

.list {
  list-style: none;
  display: flex;
  align-items: center;
}

.item {
  margin-right: 5px;
  padding: 4px 10px;
  border: 1px solid #F2F2F2;
  border-radius: 1rem;
  box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.514);
}

img {
  display: block;
  margin: auto;
  width: 90%;
  height: 50%;
}

.link {
  text-decoration: none;
}

#grass {
  background-image: url("../asserts/types-bg/grass.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#fire {
  background-image: url("../asserts/types-bg/fire.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#water {
  background-image: url("../asserts/types-bg/water.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#bug {
  background-image: url("../asserts/types-bg/bug.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#normal {
  background-image: url("../asserts/types-bg/normal.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#poison {
  background-image: url("../asserts/types-bg/poison.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#electric {
  background-image: url("../asserts/types-bg/electric.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#ground {
  background-image: url("../asserts/types-bg/ground.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#fairy {
  background-image: url("../asserts/types-bg/fairy.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#psychic {
  background-image: url("../asserts/types-bg/psychic.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}
#fighting {
  background-image: url("../asserts/types-bg/fighting.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#rock {
  background-image: url("../asserts/types-bg/rock.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#ice {
  background-image: url("../asserts/types-bg/ice.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#ghost {
  background-image: url("../asserts/types-bg/ghost.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#dragon {
  background-image: url("../asserts/types-bg/dragon.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#dark {
  background-image: url("../asserts/types-bg/dark.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#flying {
  background-image: url("../asserts/types-bg/flying.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}

#steel {
  background-image: url("../asserts/types-bg/steel.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
