<template>
  <div class="row">
    <div class="col-md-3">
      <img :src="post.featured_media_src_url" class="img-fluid">
    </div>
    <div class="col-md-9">
      <NuxtLink :to="{ name: 'posts-slug', params: { slug: post.slug } }">
        <h4>{{ post.title.rendered }}</h4>
      </NuxtLink>
      <div v-html="post.excerpt.rendered"></div>

    </div>
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
