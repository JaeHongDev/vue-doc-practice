
<template>
  <h1>button counter</h1>
  <button-counter></button-counter>


  <div :style="{ fontSize: postFontSize+'em'}">
    <BlogPost v-for="post in posts" :key="post.id" :title="post.title" @enlarge-text="postFontSize += 0.1"/>
  </div>

  <alert-box>
    <div :style="{ fontSize: postFontSize+'em'}">
      <BlogPost v-for="post in posts" :key="post.id" :title="post.title" @enlarge-text="postFontSize += 0.1"/>
    </div>
  </alert-box>
</template>
<script>
import ButtonCounter from "./ButtonCounter.vue";
import BlogPost from "./BlogPost.vue";
import AlertBox from "./AlertBox.vue";
export default {
  components: {AlertBox, BlogPost, ButtonCounter},
  data() {
    return {
      count: 0,
      posts: [
        { id: 1, title: 'My journey with Vue' },
        { id: 2, title: 'Blogging with Vue' },
        { id: 3, title: 'Why Vue is so fun' }
      ],
      postFontSize:1
    }
  }
}
</script>


<style scoped>

</style>