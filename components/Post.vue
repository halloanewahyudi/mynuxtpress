<template>
    <div class="col-md-4">
    <img :src="post.featured_media_src_url" class="img-fluid">
     <NuxtLink :to="{ name: 'posts-slug', params: { slug: post.slug } }">
        <h4>{{ post.title.rendered }}</h4>
      </NuxtLink>
      <div v-html="post.excerpt.rendered"></div>
    </div>
</template>
<script>
export default {
  props: {
    post: {
      type: Object,
      default: () => {},
    },
  },
};
</script>