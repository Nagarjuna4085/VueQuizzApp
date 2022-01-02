<template>
  <div>

<button @click="$emit('operatorSelected','+')">Additon <br> +</button>
<button @click="$emit('operatorSelected','-')">Subtraction <br> -</button>
<button @click="$emit('operatorSelected','*')">Multiplication <br> *</button>
<button @click="$emit('operatorSelected','/')">Division <br> /</button>


  </div>
</template>



<script>
export default {

}
</script>

<style>

</style>