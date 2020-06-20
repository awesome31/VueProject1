<template>
  <div>
    <form action @submit="onSubmit">
      <input type="text" @input="onInput" />
    </form>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  data: () => ({
    term: ""
  }),
  methods: {
    onInput(event) {
      this.term = event.target.value;
    },
    onSubmit(event) {
      event.preventDefault();
      this.$emit("termChange", this.term);
    }
  }
};
</script>

<style scoped>
input {
  width: 75%;
}

div {
  text-align: center;
  margin: 20px;
}
</style>
