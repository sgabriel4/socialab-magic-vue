<template>
  <v-container fluid>
    <v-card class="mb-4">
      <v-row align="center">
        <v-col class="ml-4">
          <h4>Filtrar por:</h4>
        </v-col>
        <v-col class="mr-4">
          <v-select :items="types" label="Tipo"></v-select>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<script>
import Global from "../Global.js";
import axios from "axios";

export default {
  name: "FilterComponent",
  mounted() {
    this.getTypes();
  },
  data() {
    return {
      types: [],
    };
  },
  methods: {
    getTypes() {
      axios.get(Global.url + "types").then((res) => {
        if (res.status == 200) {
          this.types = res.data.types;
          console.log(res);
        }
      });
    },
  },
};
</script>
