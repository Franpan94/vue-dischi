<template>
    <main class="ms_bg">
        <div class="container pt-5 pb-8">
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
    height: 100%;
}

.pt-5{
    padding-top: 50px;
}

.pb-8{
    padding-bottom: 80px;
}
</style>