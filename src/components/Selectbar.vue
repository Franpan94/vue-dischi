<template>
  
    <option v-model="card.genre" @click="$emit('search', card.genre)"
      >{{ card.genre }}</option>
   
  
         
     
</template>

<script>
export default {
   name: "SelectBar",
   props: ["card"],
   data: function(){
    return{
       searchoption: ''
    }
    }
}
</script>

<style>

</style>