<template>
  <div id="app" class="container">
     <Header :generdiscs = generdiscs @select= filtergenrediscs />
     <Main :discs = filterdiscs />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'

export default {
  name: 'App',

  data: function(){
    return{
      api: "https://flynn.boolean.careers/exercises/api/array/music",
      discs: [],
      generdiscs: [],
      filterdiscs: [],
    }
  },

  methods:{
    getdiscs(){
      axios.get(this.api).then((result) => {
        this.discs = result.data.response;
        this.filterdiscs = result.data.response;
        this.generdiscs = this.getgenre(this.discs);
      })
    },

    getgenre(cards){
      const generis = [];
      cards.forEach(card => {
        if(!generis.includes(card.genre)){
            generis.push(card.genre);
        }
      });
      return generis;
    },

    filtergenrediscs(filtergenre){
      console.log(filtergenre);
      if(filtergenre === ''){
        this.filterdiscs = this.discs;
      } else {
         this.filterdiscs = this.discs.filter( element => element.genre.toLowerCase() === filtergenre);
        }
      
    }
  },

  created(){
    this.getdiscs();
  },

  components: {
    Header,
    Main,
  }
}
</script>

<style lang="scss">
#app {
  @import "~bootstrap/scss/bootstrap.scss";
}
</style>
