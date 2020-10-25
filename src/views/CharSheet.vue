<template>
  <div class="csheet">
    <div class="base-info">
      <text-input
        msg="Nombre del Personaje"
        v-model="character.name"
      ></text-input>

      <text-input msg="Jugador" v-model="character.player"></text-input>

      <text-input
        msg="Clase y Nivel"
        v-model="character.class_level"
      ></text-input>

      <text-input msg="Raza" v-model="character.race" xs></text-input>
      <text-input
        msg="Alineamiento"
        v-model="character.alignment"
        xs
      ></text-input>

      <text-input msg="Deidad" v-model="character.deity" xs></text-input>
      <text-input msg="Tamano" v-model="character.size" xs></text-input>
      <text-input msg="Edad" v-model="character.age" xs></text-input>
      <text-input msg="Sexo" v-model="character.gender" xs></text-input>
      <text-input msg="Altura" v-model="character.height" xs></text-input>
      <text-input msg="Peso" v-model="character.weight" xs></text-input>
      <text-input msg="Ojos" v-model="character.eyes" xs></text-input>
      <text-input msg="Cabello" v-model="character.hair" xs></text-input>
      <text-input msg="Piel" v-model="character.skin" xs></text-input>
    </div>

    {{ character }}
  </div>
</template>

<style lang="scss" scoped>
.base-info {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-left: 5vw;
  margin-right: 5vw;
}
</style>
  
<script>
import TextInput from "@/components/TextInput.vue";

export default {
  components: {
    TextInput
  },
  data: () => ({
    character: {}
  })
};
</script>