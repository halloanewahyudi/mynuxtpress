<template>
<div>
  <article v-for="post in posts" :key="post.title.rendered">
      <div class="bg-light mb-4 pt-5" style="padding-bottom:100px">
    <div class="col-lg-7 mx-auto py-4">
         <h1>{{ post.title.rendered }}</h1>
    </div>
       
      </div>
      <div class="col-lg-7 mx-auto" style="margin-top:-100px">
        <img :src="post.featured_media_src_url" class="img-fluid mb-3" >
      </div>
        
    <section v-html="post.content.rendered" class="col-lg-7 mx-auto ">
    </section>
    <div class="text-center py-5"><button @click="goBack">Back</button></div>
    
  </article>
  </div>
</template>
<script>
export default {

  async asyncData({ $axios ,params}) {
  const posts = await $axios.$get(`https://masjid.widyabhaktisasana.com/wp-json/wp/v2/posts/?slug=${params.slug}`)
  return { posts }
},
  methods: {
    goBack() {
      return this.$router.go(-1)
    }
  }
}
</script>

