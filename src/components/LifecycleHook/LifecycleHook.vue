<template>
  <div>{{content}}</div>
  <input v-model="content"/>
</template>

<script>
export default {
  name: "LifecycleHook",
  data(){
    return {
      content:"a"
    }
  },
  setup(){
      console.log("setup");
  },
  beforeCreate() {
    console.log("before create")
  },
  created() {
    console.log("created");
  },
  beforeMount() {
    console.log("before mounted")
  },
  mounted() {
    console.log('the component is now mounted')
  },
  beforeUpdate() {
    console.log("before update",this.content);
  },
  updated() {
    console.log("update",this.content);
  }
}
</script>

<style scoped>

</style>