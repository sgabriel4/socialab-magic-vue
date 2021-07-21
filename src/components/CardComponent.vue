<template>
  <v-card class="mx-auto" max-width="90%">
    <v-container fluid>
      <v-row dense>
        <v-col v-for="card in cards" :key="card.id">
          <v-card>
            <v-img
              :src="card.imageUrl"
              v-if="card.imageUrl"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="330px"
              width="100%"
              position="center"
            >
              <v-card-title v-text="card.name"></v-card-title>
              <v-card-subtitle v-text="card.type"></v-card-subtitle>
            </v-img>
            <v-img
              src="../assets/Image-sin.jpg"
              v-if="!card.imageUrl"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="330px"
              width="100%"
              position="center"
            >
              <v-card-title v-text="card.name"></v-card-title>
              <v-card-subtitle v-text="card.type"></v-card-subtitle>
            </v-img>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn depressed color="primary">
                Ver más
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
import axios from "axios";
import Global from "../Global.js";

export default {
  name: "CardComponent",
  mounted() {
    this.getCards();
  },
  data() {
    return {
      cards: [],
    };
  },
  methods: {
    getCards() {
      axios.get(Global.url + "cards").then((res) => {
        if (res.status == 200) {
          this.cards = res.data.cards;
          console.log(this.cards);
        }
      });
    },
  },
};
</script>
