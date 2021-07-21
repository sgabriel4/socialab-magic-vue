<template>
  <v-app-bar app color="primary" dark>
    <div class="d-flex align-center">
      <v-img
        alt="Vuetify Logo"
        class="shrink mr-2"
        contain
        src="../assets/magic-logo.webp"
        transition="scale-transition"
        width="150"
      />
    </div>

    <v-spacer></v-spacer>

    <v-btn href="#" target="_blank" text>
      <span class="mr-2">Inicio</span>
    </v-btn>
  </v-app-bar>
</template>

<script>
export default {
  name: "HeaderComponent",
};
</script>
