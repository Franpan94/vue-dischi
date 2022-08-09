<template>
    <header class="ms_bg row text-center pt-3 ms_color_white">
        <div class="col-6">
            <h2>Vue Dischi</h2>
        </div>
        <div class="col-6">
            <select v-model="selectgenre" @click="changenre(selectgenre)">
                <option value="">Tutti i generi</option>
                <option  v-for="(generdisc, i) in generdiscs" :key="i" :value="generdisc.toLowerCase()">{{generdisc}}</option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    data: function(){
        return{
            selectgenre : ''
        }
    },
    name: 'MainHeader',
    props: ['generdiscs'],
    methods: {
       changenre(change){
          this.$emit('select', change);
       } 
    }
}
</script>

<style lang="scss">
.ms_bg{
    background-color: rgb(46, 58, 70);
    height: 10vh;
}

.ms_color_white{
    color: white;
}


</style>