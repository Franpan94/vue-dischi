<template>
    <main class="ms_bg">
        <div class="container">
             <Listcard />
        </div>
    </main>
</template>

<script>
import Listcard from './Listcard.vue'
export default {
    name: 'ListCard',
    components: {
        Listcard
    }
}
</script>

<style lang="scss" scoped>
.ms_bg{
    background-color: rgb(38, 51, 64);
    height: 90vh;
}
</style>