<template>
  <section>
    <div class="pb-5">
      <select v-model="searchoption">
        <option v-for="generi in generis" :key="generi.id" @click="selectchcard(searchoption)">
          {{generi.genre}}
        </option>
      </select>
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
      searchoption: '',
      cards: [],
      filtergeneris:[],
      generis: [],
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
          this.generis = response.data.response;
          
          for(let i=0 ; i < this.generis.length; i++){
             console.log(this.generis[i].genre);
          }
        });
    },

    selectchcard(opt){
      this.filtergeneris = this.generis.filter( (generi) => generi.genre.includes(opt))
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