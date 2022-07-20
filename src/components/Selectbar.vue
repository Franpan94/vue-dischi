<template>
  
    <option  @click="$emit('select', searchoption)"
      >{{ card.genre }}
    </option>
   
  
         
     
</template>

<script>
export default {
   name: "SelectBar",
   props: ["card"],
   data: function(){
    return{
       searchoption: '',
    }
  }
}
</script>

<style>

</style>