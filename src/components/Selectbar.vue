<template>
  
    <option v-model="card.genre" @click="$emit('select', card.genre)"
      >{{ card.genre }}
    </option>
   
  
         
     
</template>

<script>
export default {
   name: "SelectBar",
   props: ["card"],
   data: function(){
    return{
  
    }
  }
}
</script>

<style>

</style>