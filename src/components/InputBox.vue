<template>
  <div class="input-box" v-bind:class="{
      grey: grey
    }">
    <span v-if="msg && show_title">{{ msg }}</span>
    <input
      v-model="inputValue"
      @input="onInputChange()"
      v-bind:type="type"
      v-bind:class="{
      grey: grey
    }"
    />
  </div>
</template>

<script>
export default {
  name: "TextInput",
  props: {
    msg: String,
    modelValue: String,
    xs: Boolean,
    black: Boolean,
    grey: Boolean,
    show_title: Boolean,
    type: String
  },
  data: function() {
    return {
      inputValue: this.modelValue
    };
  },
  methods: {
    onInputChange() {
      this.$emit("update:modelValue", this.inputValue);
    }
  },
  watch: {
    modelValue: function(val) {
      this.inputValue = val;
    }
  }
};
</script>

<style scoped lang="scss">
@import "@/assets/styles/_media.scss";
@import "@/assets/styles/_colors.scss";

$size: 35px;

.input-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;

  margin-left: 5px;
  margin-right: 9px;

  width: $size;
  // height: $size;

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

.xs {
  width: 70px;

  @media #{$small-screen} {
    width: 25vw;
  }

  @media #{$xsmall-screen} {
    width: 38vw;
  }
}

input {
  border: none;
  border: 1px solid $black;
  font-size: 12px;
  font-weight: 400;
  width: 100%;
  height: 0.7 * $size;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  text-transform: uppercase;
  text-align: center;

  &.grey {
    border: 5px solid $grey;
  }
}

span {
  text-transform: uppercase;
  font-size: 8px;
  font-weight: 700;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  letter-spacing: -1px;
  margin-bottom: 3px;
}
</style>
