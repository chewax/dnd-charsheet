<template>
  <div class="base-info">
    <text-input msg="Nombre del Personaje" v-model="character.name"></text-input>
    <text-input msg="Jugador" v-model="character.player"></text-input>
    <text-input msg="Clase" v-model="character.class" xs></text-input>
    <text-input msg="Nivel" v-model="character.level" xs type="number"></text-input>
    <text-input msg="Raza" v-model="character.race" xs></text-input>
    <text-input msg="Alin." v-model="character.alignment" xs></text-input>
    <text-input msg="Deidad" v-model="character.deity" xs></text-input>
    <text-input msg="Tamano" v-model="character.size" xs></text-input>
    <text-input msg="Edad" v-model="character.age" xs type="number"></text-input>
    <text-input msg="Sexo" v-model="character.gender" xs></text-input>
    <text-input msg="Altura" v-model="character.height" xs type="number"></text-input>
    <text-input msg="Peso" v-model="character.weight" xs type="number"></text-input>
    <text-input msg="Ojos" v-model="character.eyes" xs></text-input>
    <text-input msg="Cabello" v-model="character.hair" xs></text-input>
    <text-input msg="Piel" v-model="character.skin" xs></text-input>
  </div>
</template>

<script>
import TextInput from "@/components/TextInput.vue";

export default {
  name: "CharSummary",
  components: {
    TextInput
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
.base-info {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-left: 5vw;
  margin-right: 5vw;
}
</style>
