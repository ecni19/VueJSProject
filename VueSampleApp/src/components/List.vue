<script>
import ListCard from "./ListCard.vue";
import HelloWorld from "./HelloWorld.vue";
import MoreInfo from "./MoreInfo.vue";

export default {
  data() {
    return {
      activities: [],
      isClick: false,
      activityNum: null,
    };
  },

  components: {
    ListCard,
    HelloWorld,
    MoreInfo,
  },
  methods: {
    handleClick: function (index) {
      this.isClick = !this.isClick;
      this.activityNum = index;
      console.log(this.activities[index].actor.displayName);
    },
    backButton: () => {
      this.isClick = !this.isClick;
    }
  },
  // fetch from api before component render
  async created() {
    const res = await fetch(
      "https://aggiefeed.ucdavis.edu/api/v1/activity/public?l=25"
    );
    const data = await res.json();
    this.activities = data;
  },
};
</script>

<template>
  <div>
      <div v-for="(item, index) in activities" :key="item.id">
        <ListCard
          v-if="!isClick"
          @click="handleClick(index)"
          :title="item.title"
          :displayName="item.actor.displayName"
          :index=index
        />
      </div>
    <!-- listening to @change-back event -->
    <MoreInfo
      v-if="isClick"
      :activities = "activities"
      :ind = "activityNum"
      @change-back="isClick = !isClick"
    />
  </div>
</template>
