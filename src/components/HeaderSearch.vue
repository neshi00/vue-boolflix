<template>
  <header>
    <span>Boolflix</span>
    <div>
      <input
        type="text"
        placeholder="Cerca"
        v-model="searched"
        @keyup.enter="$emit('search', searched)"
      />
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
    font-size: 35px;
  }

  input {
    margin: 10px 0;
    border-radius: 5px;
    padding: 2px 0;
  }
}
</style>
