<template>
  <div>
        <h4>{{ title }}</h4>
        <p>{{ description }}</p>
        <article-preview v-for="post in posts" :key="post._slug" :post="post"></article-preview>
      </div>
</template>
<script>
import ArticlePreview from "~/components/ArticlePreview.vue";
export default {
  components: {
    ArticlePreview
  },
  props: ["posts", "title", "description"]
};
</script>
<style>
</style>