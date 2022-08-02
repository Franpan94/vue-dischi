<template>
  <div>
     <h5>{{disc.title}}</h5>
     <img class="img-fluid" :src="disc.poster" :alt="disc.title">
  </div>
</template>

<script>
export default {
  name: 'DiscElement',
  props: ['disc']
}
</script>

<style>

</style>