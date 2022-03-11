<script>
import List from "./components/List.vue";

export default {
  components: {
    List,
  },
};
</script>

<template>
  <div class="cont">
    <List />
  </div>
</template>


<style scoped>
  .cont {
    width: 100%;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>