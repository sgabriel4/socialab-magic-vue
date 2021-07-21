<template>
  <v-app>
    <v-main>
      <HeaderComponent />
      <br>
      <FilterComponent />
      <CardComponent />
      <HelloWorld />
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import HeaderComponent from "./components/HeaderComponent";
import FilterComponent from "./components/FilterComponent";
import CardComponent from "./components/CardComponent.vue";

export default {
  name: "App",

  components: {
    HelloWorld,
    HeaderComponent,
    FilterComponent,
    CardComponent,
  },

  data: () => ({
    //
  }),
};
</script>
