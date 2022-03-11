<script>
export default {
  props: {
    title: String,
    displayName: String,
    index: Number,
  },
};
</script>

<template>
  <div class="card">
    <h1 v-html="(index+1) + '. ' + title"></h1>
    <p v-html="displayName"></p>
  </div>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  max-width: 500px;
  padding: 50px;
  border-radius: 10px;
  border: solid black 1px;
  margin-top: 10px;
}
.card:hover {
  cursor: pointer;
}
h1 {
  margin: 0;
  padding: 0;
}
p {
  padding: 0;
  margin: 20px 0 0 0;
}
</style>
