<template>
  <div>
    <section>
      <Slideshow />
      <JadwalSholat
        style="margin-top: -40px"
        :subuh="posts.data.jadwal.subuh"
        :dzuhur="posts.data.jadwal.dzuhur"
        :ashar="posts.data.jadwal.ashar"
        :maghrib="posts.data.jadwal.maghrib"
        :isya="posts.data.jadwal.isya"
      />
    </section>
    <section>
      <div class="container">
        <div class="row pt-5">
          <div class="col-md-6">
            <Berita v-for="art in berita" :key="art.id" :post="art" />
          </div>
          <div class="col-md-6">
            <Berita v-for="art in artikel" :key="art.id" :post="art" />
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
let current_datetime = new Date();
let formatted_date =
  current_datetime.getFullYear() +
  "/" +
  (current_datetime.getMonth() + 1) +
  "/" +
  current_datetime.getDate();
console.log(formatted_date);
export default {
  async asyncData({ $axios }) {
    const posts = await $axios.$get(
      `https://api.myquran.com/v1/sholat/jadwal/1222/${formatted_date}`
    );
    const berita = await $axios.$get(
      "https://masjid.widyabhaktisasana.com/wp-json/wp/v2/posts?categories=3"
    );
    const artikel = await $axios.$get(
      "https://masjid.widyabhaktisasana.com/wp-json/wp/v2/posts?categories=10"
    );
    return { posts, berita, artikel };
  },

  data() {
    return {
      artikel: [],
      berita: [],
    };
  },
};
</script>
<style >
.carousel-caption {
  bottom: 50px;
}
</style>
