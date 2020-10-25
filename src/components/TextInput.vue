<template>
  <div
    class="text-input"
    v-bind:class="{
      xs: xs
    }"
  >
    <input v-model="inputValue" @input="onInputChange()" type="text" />
    <span>{{ msg }}</span>
  </div>
</template>

<script>
export default {
  name: "TextInput",
  props: {
    msg: String,
    modelValue: String,
    xs: Boolean
  },
  data: function() {
    return {
      inputValue: this.value
    };
  },
  methods: {
    onInputChange() {
      this.$emit("update:modelValue", this.inputValue);
    }
  }
};
</script>

<style scoped lang="scss">
$xsmall-screen: "only screen and (max-width : 350px)";
$small-screen: "only screen and (max-width : 600px)";
$large-screen: "only screen and (min-width : 950px)";
$xlarge-screen: "only screen and (min-width : 1500px)";

.text-input {
  display: flex;
  margin-bottom: 35px;
  margin-left: 1vw;
  margin-right: 1vw;
  flex-direction: column;
  align-items: flex-start;
  width: 40vw;

  @media #{$small-screen} {
    width: 90vw;
  }

  @media #{$large-screen} {
    width: 27vw;
  }

  @media #{$xlarge-screen} {
    width: 20vw;
  }
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
  border-bottom: 1px solid #5a5a5a;
  font-size: 12px;
  font-weight: 400;
  width: 100%;
  // font-family: Verdana, Geneva, Tahoma, sans-serif;
  text-transform: uppercase;
}

span {
  text-transform: uppercase;
  font-size: 8px;
  font-weight: 700;
  // font-family: Verdana, Geneva, Tahoma, sans-serif;
  letter-spacing: 2px;
  margin-top: 5px;
  margin-left: 3px;
}
</style>
