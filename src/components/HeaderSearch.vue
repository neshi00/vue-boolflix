<template>
  <header>
    <span>Boolflix</span>
    <div>
      <input
        type="text"
        placeholder="Scrivi il titolo di un film"
        v-model="searched"
      />
      <button @click="$emit('search', searched)">Clicca per cercare</button>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      searched: "",
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: #000;
  display: flex;
  justify-content: space-between;
  padding: 20px;

  span {
    color: red;
    font-weight: bold;
    font-size: 30px;
  }
}
</style>
