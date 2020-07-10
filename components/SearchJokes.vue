<template>
  <form @submit.prevent="onSubmit">
    <input
      class="searchbar"
      type="text"
      v-model="text"
      placeholder="Search Jokes..."
    />
    <input class="submitbtn" type="submit" value="Search Joke" />
  </form>
</template>

<script>
export default {
  name: "SearchJokes",
  data() {
    return {
      text: ""
    };
  },
  methods: {
    onSubmit() {
      this.$emit("search-text", this.text);
      this.text = "";
    }
  }
};
</script>

<style>
.searchbar {
  padding: 10px;
}
.submitbtn {
  color: white;
  background-color: #333;
  border: none;
  padding: 10px 15px;
}
</style>
