<template>
  <section>
    <div class="pb-5">
      <select ><Selectbar v-for="card in cards" 
      :key="card.id" :card="card" 
      @search = "searchcard"/></select>
    </div>
    <div class="row ">
      <Card v-for="card in cards" :key="card.id" :card="card" class="col-3" />
    </div>
  </section>
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
      filtercards:[],
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
          this.filtercards = this.cards;
        });
    },

    searchcard(opt){
      this.filtercards = this.cards.filter( (card) => card.genre.includes(opt))
    }
  },

  created() {
    this.getcard();
  },
};
</script>

<style lang="scss" scoped>
.ms_d-inline{
  display: block;
}
</style>