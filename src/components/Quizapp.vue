<template>
  <div>
    
    <div v-if="isQuizstarted">
    <h4> {{oprandLeft}} {{operate}}  {{oprandRight}} </h4>
     <button v-for="answer of answers" :key="answer">{{answer}}</button>
    
     <p>{{result}}</p>
            
    </div>

    <div v-if="!isQuizstarted">
        <button  @click="startquiz">Start Quiz</button>

    </div>
        <button @click="$emit('onBack')">Back</button>
  </div>
</template>

<script>
export default {

    props:['operate'],
    data () {
            return {
                isQuizstarted:false,
                oprandLeft:null,
                oprandRight:null,
                answers:[],
                result:'',

            }
        },
    methods : {
            startquiz : function(){
                this.isQuizstarted=true;
                this.oprandLeft = parseInt(Math.random()*13) ;
                this.oprandRight = parseInt(Math.random()*13);
                
                for(let i=0;i<5;i++){
                    const answer = 
                        parseInt(Math.random()*3) *
                        parseInt(Math.random()*7)
                    ;
                    this.answers.push(answer);
                    }

                if(this.operate === '+'){
                    const result = this.oprandLeft + this.oprandRight;
                    this.answers[parseInt(Math.random()*3)]=result
                     }
                else if(this.operate === '-'){
                   const result = this.oprandLeft - this.oprandRight;
                    this.answers[parseInt(Math.random()*3)]=result
                    }
                 else if(this.operate === '*'){
                   const result = this.oprandLeft * this.oprandRight;
                    this.answers[parseInt(Math.random()*3)]=result

                    }
                else{
                    const result = this.oprandLeft / this.oprandRight;
                    this.answers[parseInt(Math.random()*3)]=result

                    }
                
                    

               },
               
                


        }
}
</script>

<style>

</style>