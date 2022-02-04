<template>
  <header>
    <span>Boolflix</span>
    <div>
      <input
        type="text"
        placeholder="Scrivi il titolo di un film"
        v-model="searched"
      />
      <button @click="$emit('search')">Clicca per cercare</button>
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
  }
}
</style>
