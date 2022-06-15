<template>
  <br>
  <br>
  <br>

  <input v-model="question">
  <div > {{answer}}</div>
  <button @click="getAnswer"></button>
</template>

<script>
export default {
  data(){
    return {
      question:'',
      answer:'',
    }
  },
  watch:{
    question(newQuestion, oldQuestion) {
      if (newQuestion.indexOf('?') > -1) {
        this.getAnswer()
      }
    },
    answer(newAnswer,oldAnswer){
      console.log("new",newAnswer);
      console.log("old",oldAnswer);
    }
  },
  methods:{
    async getAnswer(){
      this.answer ='Thinking';
      try{
        const res = await fetch('https://yesno.wtf/api');
        this.answer = (await res.json()).answer;
      }catch (error){
        this.answer = 'Error! Could not reach the API.' + error;
      }
    }
  }
}
</script>

<style scoped>

</style>