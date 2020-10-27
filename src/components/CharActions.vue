<template>
  <div class="char-actions">
    <!-- <button class="char-action-button" @click="uploadJSON()">Subir JSON</button> -->
    <button class="char-action-button" @click="downloadJSON()">Descargar</button>
    <input type="file" accept="application/json" @change="onFileChange" />
  </div>
</template>

<script>
export default {
  name: "CharSummary",
  components: {},
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
    },

    onFileChange(e) {
      let files = e.target.files || e.dataTransfer.files;
      if (!files.length) return;
      this.readFile(files[0]);
    },
    readFile(file) {
      let reader = new FileReader();
      reader.onload = e => {
        this.character = JSON.parse(e.target.result);
        this.onInputChange();
      };
      reader.readAsText(file);
    },

    downloadJSON() {
      const data = JSON.stringify(this.character);
      const blob = new Blob([data], { type: "text/plain" });
      const e = document.createEvent("MouseEvents"),
        a = document.createElement("a");
      a.download = `${
        this.character.name ? this.character.name : "character"
      }.json`;
      a.href = window.URL.createObjectURL(blob);
      a.dataset.downloadurl = ["text/json", a.download, a.href].join(":");
      e.initEvent(
        "click",
        true,
        false,
        window,
        0,
        0,
        0,
        0,
        0,
        false,
        false,
        false,
        false,
        0,
        null
      );
      a.dispatchEvent(e);
    }
  }
};
</script>

<style scoped lang="scss">
@import "@/assets/styles/_colors.scss";

.char-actions {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}

.char-action-button {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0.6em;
  background-color: $epic-purple;
  color: $white;
  border-radius: 10px;
  border: none;
  border: 2px solid darken($epic-purple, 10);
  margin-top: 5px;
  cursor: pointer;
}
</style>
