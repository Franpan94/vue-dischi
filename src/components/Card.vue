<template>
  <div class="ms_bg">
    
      <img :src="card.poster" class="card-img-top height" alt="" />
    
    <div class="card-body">
      <h4 class="card-title">{{ card.title }}</h4>
      <h5 class="card-text">
        {{ card.author }}
      </h5>
      <h5 class="card-text">
        {{ card.year }}
      </h5>
    </div>
  </div>
</template>

<script>
export default {
  name: "MainCard",
  props: ["card"],
};
</script>

<style lang="scss" scoped>
.ms_bg{
    background-color: rgb(46, 58, 70);;
    height: 60vh;
    padding: 10px;
    color: white;
}

.height{
    height: 40vh;
}

h4{
    text-transform: uppercase;
}

h5{
    color: grey;
}

</style>