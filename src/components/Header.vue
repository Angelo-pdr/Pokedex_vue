<script setup lang="ts"></script>

<template>
  <header class="header">
    <img src="../asserts/logo.png" alt="logo" id="logo" />
    <div class="search">
      <input type="text" placeholder="Procura pokemon" />
      <button>
        <img src="../asserts/imgs/searchIcon.png" alt="coracao" id="heart" />
      </button>
    </div>
    <div id="totalFavorites">
      <img src="../asserts/imgs/love.png" alt="heart" />0
    </div>
  </header>
</template>

<style scoped>
.header {
  width: 100%;
  max-height: 70px;
  height: 100%;
  padding: 13px;
  background-color: transparent;
  display: flex;
  align-items: center;
  justify-content: space-around;
  gap: 10px;
}

#logo {
  display: block;
  max-width: 10%;
  height: auto;
}

.search {
  background-color: white;
  max-height: 35px;
  max-width: 100%;
  padding: 13px;
  border-radius: 1.5rem;
  display: flex;
  align-items: center;
}

input {
  flex: 1;
  outline: none;
  height: 100%;
  font-size: 1rem;
  padding: 2px;
  color: black;
  border: none;
  margin-right: 5px;
}

button {
  cursor: pointer;
  border: none;
  background-color: white;
}

#heart {
  background-color: white;
  color: white;
}

#totalFavorites {
  display: flex;
  align-items: center;
  cursor: pointer;
}
</style>
