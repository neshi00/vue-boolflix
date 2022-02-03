<template>
  <div>
    <input
      type="text"
      placeholder="Scrivi il titolo di un film"
      v-model="searched"
    />
    <button @click="$emit('search')">Clicca per cercare</button>
  </div>
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

<style lang="scss" scoped></style>
