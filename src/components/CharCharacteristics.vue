<template>
  <div class="ccs-wrapper">
    <char-characteristic
      v-model="character"
      name="fuerza"
      label="FUE"
      alt="Fuerza"
      type="number"
      show_title
    ></char-characteristic>
    <char-characteristic
      v-model="character"
      name="destreza"
      label="DES"
      alt="Destreza"
      type="number"
    ></char-characteristic>
    <char-characteristic
      v-model="character"
      name="constitucion"
      label="CON"
      alt="Constitucion"
      type="number"
    ></char-characteristic>
    <char-characteristic
      v-model="character"
      name="inteligencia"
      label="INT"
      alt="Inteligencia"
      type="number"
    ></char-characteristic>
    <char-characteristic
      v-model="character"
      name="sabiduria"
      label="SAB"
      alt="Sabiduria"
      type="number"
    ></char-characteristic>
    <char-characteristic v-model="character" name="carisma" label="CAR" alt="carisma" type="number"></char-characteristic>
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
      character: { ...this.modelValue, characteristics: {} }
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
}
</style>
