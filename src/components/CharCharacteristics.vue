<template>
  <div class="ccs-wrapper">
    <char-characteristic
      v-model="character"
      name="strength"
      label="FUE"
      alt="Fuerza"
      type="number"
      show_title
    ></char-characteristic>
    <char-characteristic
      v-model="character"
      name="dexterity"
      label="DES"
      alt="Destreza"
      type="number"
    ></char-characteristic>
    <char-characteristic
      v-model="character"
      name="constitution"
      label="CON"
      alt="Constitucion"
      type="number"
    ></char-characteristic>
    <char-characteristic
      v-model="character"
      name="intelligence"
      label="INT"
      alt="Inteligencia"
      type="number"
    ></char-characteristic>
    <char-characteristic
      v-model="character"
      name="wisdom"
      label="SAB"
      alt="Sabiduria"
      type="number"
    ></char-characteristic>
    <char-characteristic
      v-model="character"
      name="charistma"
      label="CAR"
      alt="carisma"
      type="number"
    ></char-characteristic>
  </div>
</template>

<script>
import CharCharacteristic from "@/components/CharCharacteristic.vue";

export default {
  name: "CharSummary",
  components: {
    CharCharacteristic
  },
  props: {
    modelValue: Object
  },
  data: function() {
    return {
      character: this.modelValue
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
.ccs-wrapper {
  display: flex;
  flex-wrap: nowrap;
  justify-content: flex-start;
  flex-direction: column;
  margin-left: 5vw;
  margin-top: 2vh;
}
</style>
