<template>
  <div class="cc-wrapper">
    <box-label :label="label" :alt="alt"></box-label>
    <input-box
      msg="PUNT. CARACT."
      v-model="character.characteristics[name].punt"
      :show_title="show_title"
      :type="type"
    ></input-box>
    <input-box
      msg="MOD. CARACT."
      v-model="character.characteristics[name].mod"
      :show_title="show_title"
      :type="type"
    ></input-box>
    <input-box
      msg="PUNT. TEMPORAL"
      v-model="character.characteristics[name].punt_temp"
      grey
      :show_title="show_title"
      :type="type"
    ></input-box>
    <input-box
      msg="MOD. TEMPORAL"
      v-model="character.characteristics[name].mod_temp"
      grey
      :show_title="show_title"
      :type="type"
    ></input-box>
  </div>
</template>

<script>
import InputBox from "@/components/InputBox.vue";
import BoxLabel from "@/components/BoxLabel.vue";

export default {
  name: "CharSummary",
  components: {
    InputBox,
    BoxLabel
  },
  props: {
    name: String,
    label: String,
    alt: String,
    show_title: Boolean,
    modelValue: Object,
    type: String
  },
  data: function() {
    return {
      character: {
        ...this.modelValue,
        characteristics: { [this.name]: {} }
      }
    };
  },
  methods: {
    onInputChange() {
      this.$emit("update:modelValue", this.character);
    }
  },
  watch: {
    modelValue: function(val) {
      this.character = val;
    }
  }
};
</script>

<style scoped lang="scss">
.cc-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-items: center;
}
</style>
