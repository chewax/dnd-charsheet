<template>
  <div class="lb-wrapper">
    <span class="label" v-if="label">{{ label }}</span>
    <span class="alt" v-if="alt">{{ alt }}</span>
  </div>
</template>

<script>
export default {
  name: "TextInput",
  props: {
    label: String,
    alt: String
  }
};
</script>

<style scoped lang="scss">
@import "@/assets/styles/_media.scss";
@import "@/assets/styles/_colors.scss";

$size: 35px;

.lb-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  margin-left: 5px;
  margin-right: 5px;
  background-color: $black;
  width: 2 * $size;
  height: $size;
  align-self: flex-end;

  // @media #{$small-screen} {
  //   width: 90vw;
  // }

  // @media #{$large-screen} {
  //   width: 27vw;
  // }

  // @media #{$xlarge-screen} {
  //   width: 20vw;
  // }
}

.label {
  text-transform: uppercase;
  color: $white;
  font-size: 20px;
  font-weight: 800;
}

.alt {
  text-transform: uppercase;
  color: $white;
  font-size: 8px;
  font-weight: 200;
  margin-top: -4px;
}

// .xs {
//   width: 70px;

//   @media #{$small-screen} {
//     width: 25vw;
//   }

//   @media #{$xsmall-screen} {
//     width: 38vw;
//   }
// }

// input {
//   border: none;
//   border: 1px solid $black;
//   font-size: 12px;
//   font-weight: 400;
//   width: 100%;
//   height: 0.6 * $size;
//   font-family: Verdana, Geneva, Tahoma, sans-serif;
//   text-transform: uppercase;

//   &.grey {
//     border-top: 3px solid $grey;
//     border-left: 5px solid $grey;
//     border-bottom: 3px solid $grey;
//     border-right: 5px solid $grey;
//     margin-top: -3px;
//   }
// }

// span {
//   text-transform: uppercase;
//   font-size: 8px;
//   font-weight: 700;
//   font-family: Verdana, Geneva, Tahoma, sans-serif;
//   letter-spacing: -1px;
//   margin-bottom: 3px;
//   // margin-left: 3px;
// }
</style>
