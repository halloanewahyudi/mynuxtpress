<template>
  <div>
    <div class="bg-light mb-4">
      <div class="col-lg-7 mx-auto py-4">
        <h1>Blog</h1>
      </div>
    </div>

    <div class="col-lg-7 mx-auto d-md-flex flex-wrap">
      <div class="row">
        <Post v-for="post in posts" :key="post.id" :post="post" />
      </div>
      {{length}}
    </div>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {
    const posts = await $axios.$get(
      "https://masjid.widyabhaktisasana.com/wp-json/wp/v2/posts?per_page=6"
    );
    return { posts };
  },
  data() {
    return {
      posts: [],

    };
  },
};
</script>
