<template>
  <div id="app">
<P>Marhs Quiz App</P>

<Quizapp @onBack="clearOperator" v-if="operator" :operate="operator" />
 <OperatorSelector v-if="!operator" @operatorSelected="operatorSelected" />
  </div>


</template>

<script>
import OperatorSelector  from './components/OperatorSelector.vue';
import Quizapp  from './components/Quizapp.vue';
export default {
  name: 'App',
  data (){
    return{
      operator : null,
      }

    },
    methods: {
      operatorSelected : function(operator) {
             this.operator=operator;

        },
        clearOperator : function(){
          this.operator=null;

          }

    },
  components: {
    OperatorSelector,Quizapp
    
    
  }
}
</script>

<style>
#app {
  margin: 30;
  padding-left: 30px;

}
button {

margin-right: 20px;
background-color:#08BA9E;

  }
</style>
