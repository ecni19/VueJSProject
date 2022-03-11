<script>
export default {
  props: {
    activities: Object,
    ind: Number,
  },
}
</script>

<template>
  <div class="moreInfo">
    <h1 v-html="activities[ind].title"></h1>
    <p v-html="activities[ind].actor.displayName"></p>
    <p v-html="activities[ind].object.objectType"></p>
    <p v-html="activities[ind].published"></p>
    <!-- emitting the change-back event by clicking the button -->
    <button class="btn" @click="$emit('change-back')">Home</button>
  </div>
</template>

<style scoped>
.moreInfo {
  display: flex;
  flex-direction: column;
  max-width: 500px;
  align-items: center;
  text-align: center;
  padding: 50px;
  border-radius: 10px;
  border: solid black 1px;
}

.btn {
  padding: 10px;
  width: 150px;
}
</style>