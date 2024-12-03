<script setup>
import { ref } from "vue";
import CodeMirror from "vue-codemirror6";

// Importy dla języka Python i motywów
import { python } from "@codemirror/lang-python";
import { oneDark } from "@codemirror/theme-one-dark";
import { basicSetup } from "codemirror";

// Reaktywne zmienne
const value = ref(""); // Początkowa wartość kodu
const dark = ref(window.matchMedia("(prefers-color-scheme: dark)").matches);

// Konfiguracja rozszerzeń CodeMirror
const extensions = ref([basicSetup, python(), dark.value ? oneDark : []]);

// Placeholder z pustymi liniami
const defaultContent = Array(20).fill("").join("\n");
if (value.value === "") {
  value.value = defaultContent;
}
</script>

<template>
  <div>
    <code-mirror
      v-model="value"
      :extensions="extensions"
      :theme="{ dark }"
      class="editor"
    />
  </div>
</template>

<style scoped>
.editor {
  border: 1px solid #ddd;
  border-radius: 4px;
  height: calc(20 * 1.5em); /* Wysokość na 20 linii */
  min-height: calc(20 * 1.5em);
  font-size: 16px;
  line-height: 1.5;
  overflow: auto;
  background-color: black;
  white-space: pre; /* Utrzymanie pustych linii */
}
</style>
