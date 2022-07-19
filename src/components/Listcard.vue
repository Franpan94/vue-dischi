<template>
  <div class="row ">
    <Card v-for="card in cards" :key="card.id" :card="card" class="col-3" />
  </div>
</template>

<script>
import axios from "axios";
import Card from "./Card.vue";

export default {
  name: "MainListard",
  data: function () {
    return {
      cards: [],
    };
  },

  components: {
    Card,
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