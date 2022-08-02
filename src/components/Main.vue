<template>
    <main class="ms_bg row ms_color_white">
        <DiscElement class="col-2 m-3" v-for="(disc, index) in discs" :key="index" :disc = disc />
    </main>
</template>

<script>
import DiscElement from './DiscElement.vue'
export default {
    name: 'Main',
    components: {
       DiscElement 
    },

    props: ['discs']
}
</script>

<style lang="scss" scoped>
.ms_bg{
    background-color: rgb(38, 51, 64);
    height: 100vh;
}

.pt-5{
    padding-top: 50px;
}

.pb-8{
    padding-bottom: 80px;
}
</style>