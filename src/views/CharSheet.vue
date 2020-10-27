<template>
  <div class="char-sheet">
    <div class="info-header">
      <char-summary :character="character"></char-summary>
      <char-actions v-model="character"></char-actions>
    </div>
    <char-base-info v-model="character"></char-base-info>

    <div class="char-traits-group">
      <char-characteristics v-model="character"></char-characteristics>
    </div>
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

.char-traits-group {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
</style>
  
<script>
import CharSummary from "@/components/CharSummary.vue";
import CharBaseInfo from "@/components/CharBaseInfo.vue";
import CharActions from "@/components/CharActions.vue";
import CharCharacteristics from "@/components/CharCharacteristics.vue";

export default {
  components: {
    CharBaseInfo,
    CharCharacteristics,
    CharSummary,
    CharActions
  },
  data: () => ({
    character: {
      image_url: "https://pbs.twimg.com/media/EN6HSm4W4AAkfP5.png",
      level: "1",
      characteristics: {
        strength: {
          punt: 0,
          mod: 0,
          punt_temp: 0,
          mod_temp: 0
        },
        dexterity: {
          punt: 0,
          mod: 0,
          punt_temp: 0,
          mod_temp: 0
        },
        constitution: {
          punt: 0,
          mod: 0,
          punt_temp: 0,
          mod_temp: 0
        },
        intelligence: {
          punt: 0,
          mod: 0,
          punt_temp: 0,
          mod_temp: 0
        },
        wisdom: {
          punt: 0,
          mod: 0,
          punt_temp: 0,
          mod_temp: 0
        },
        charistma: {
          punt: 0,
          mod: 0,
          punt_temp: 0,
          mod_temp: 0
        }
      }
    }
  })
};
</script>