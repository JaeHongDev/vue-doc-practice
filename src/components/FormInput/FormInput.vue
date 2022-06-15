<template>
  <div>form input</div>
  <input
      type="checkbox"
      v-model="toggle"
      true-value="yes"
      false-value="no" />
  {{toggle}}
</template>

<script>
export default {
  name: "FormInput",
  data(){
    return{
      toggle:false,
    }
  },

  computed:{
    change(){
      this.text = this.text+"===";
    }
  }
}
</script>

<style scoped>

</style>