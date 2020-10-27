<template>
  <div class="char-sheet">
    <div class="info-header">
      <char-summary :character="character"></char-summary>
      <char-actions v-model="character"></char-actions>
    </div>

    <char-base-info v-model="character"></char-base-info>
    {{ character }}
  </div>
</template>

<style lang="scss" scoped>
.char-sheet {
  display: flex;
  flex-direction: column;
}

.info-header {
  display: flex;
  justify-content: space-between;
  margin: 4vh 5vw 4vh 5vw;
}
</style>
  
<script>
import CharSummary from "@/components/CharSummary.vue";
import CharBaseInfo from "@/components/CharBaseInfo.vue";
import CharActions from "@/components/CharActions.vue";

export default {
  components: {
    CharBaseInfo,
    CharSummary,
    CharActions
  },
  data: () => ({
    character: {
      image_url: "https://pbs.twimg.com/media/EN6HSm4W4AAkfP5.png",
      level: "1"
    }
  })
};
</script>