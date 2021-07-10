<template>
    <div class="col-md-7 mx-auto border rounded bg-white">
        <div class="d-flex justify-content-between" >
            <div class="p-3 text-center d-flex justify-content-between w-100" >
                 <div class="js-item text-center p-3 ">
                     <strong>Subuh</strong>
                     <div>{{subuh}}</div>
                 </div>
                 <div class="js-item text-center p-3">
                     <strong>Dzuhur</strong>
                     <div > {{dzuhur}}</div>
                 </div>
                 <div class="js-item text-center p-3">
                     <strong>Ashar</strong>
                     <div ashar="ashar">{{ashar}}</div>
                 </div>
                 <div class="js-item text-center p-3">
                     <strong>Maghrib</strong>
                     <div>{{maghrib}}</div>
                 </div>
                 <div class="js-item text-center p-3">
                     <strong>Isya</strong>
                     <div>{{isya}}</div>
                 </div>
            </div>
        </div>
    </div>
</template>
<script>

  let current_datetime = new Date()
  let formatted_date = current_datetime.getFullYear() + "/" + (current_datetime.getMonth() + 1) + "/" + current_datetime.getDate()
export default {
 async asyncData({ $axios }) {
 const ip = await $axios.$get(`https://api.myquran.com/v1/sholat/jadwal/1222/${formatted_date}`)
  return { ip }
},

  props:['subuh','dzuhur','ashar','maghrib','isya'],

 methods: {
  async fetchSomething() {
    const ip = await this.$axios.$get(`https://api.myquran.com/v1/sholat/jadwal/1222/${formatted_date}`)
    this.ip = ip.data
    return {ip}
  }
}

}
</script>