<template>
  <div class="row ">
    <Selectbar />
    <Card v-for="card in cards" :key="card.id" :card="card" class="col-3" />
  </div>
</template>

<script>
import axios from "axios";
import Card from "./Card.vue";
import Selectbar from "./Selectbar.vue";

export default {
  name: "MainListard",
  data: function () {
    return {
      cards: [],
    };
  },

  components: {
    Card,
    Selectbar
  },

  methods: {
    getcard() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((response) => {
          this.cards = response.data.response;
        });
    },
  },

  created() {
    this.getcard();
  },
};
</script>

<style lang="scss" scoped>
</style>