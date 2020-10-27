<template>
  <div class="char">
    <div class="avatar">
      <img :src="character.image_url" />
      <span class="char-level">{{character.level}}</span>
    </div>

    <div class="char-info">
      <span class="char-name">{{character.name}}</span>
      <span class="char-class-race">{{character.class}} {{character.race}}</span>
      <span class="char-player" v-if="character.player">({{character.player}})</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "CharSummary",
  props: {
    character: Object
  }
};
</script>

<style scoped lang="scss">
@import "@/assets/styles/_colors.scss";
.avatar {
  position: relative;

  img {
    border-radius: 50%;
    height: 100px;
    object-fit: cover;
    object-position: center;
    width: 100px;
    border: 3px solid $epic-purple;
  }

  .char-level {
    position: absolute;
    display: inline-block;
    min-width: 1.3em; /* em unit */
    padding: 0.4em; /* em unit */
    border-radius: 50%;
    font-size: 18px;
    font-weight: 500;
    text-align: center;
    background: $epic-purple;
    color: #fefefe;
    min-height: 1em;
    right: -10px;
    border: 3px solid white;
  }
}
.char {
  display: flex;
  justify-content: flex-start;
}

.char-info {
  color: $epic-purple;
  display: flex;
  flex-direction: column;
  margin-left: 20px;
  text-align: left;
  font-weight: 600;

  .char-name {
    text-transform: uppercase;
    letter-spacing: -1px;
    font-size: 25px;
  }

  .char-class-race {
    text-transform: uppercase;
    font-weight: 400;
    margin-top: 2px;
  }

  .char-player {
    text-transform: uppercase;
    font-weight: 200;
    font-size: 13px;
    margin-top: 3px;
  }
}
</style>
