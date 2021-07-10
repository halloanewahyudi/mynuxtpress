<template>
<div>
  <div class="bg-light mb-4">
      <div class="col-lg-7 mx-auto py-4">
        <h1>About</h1>
      </div>
    </div>
    <div class="mb-4">
      <div class="col-lg-7 mx-auto py-4">
       <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae voluptatum suscipit dolore unde debitis. Reprehenderit, sit neque 
         fuga deleniti tenetur repellat cupiditate dolore at dolorem, sequi harum minus! Tempora, quod.</p>
         <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ratione enim voluptas dicta cumque, 
           est dolore explicabo. Veniam minus officiis placeat, enim, tempore dolore nemo aliquid obcaecati 
           recusandae, qui voluptas eius!</p>
         <img v-bind:src="'https://picsum.photos/1024/480/?image=58'" class="img-fluid">
      </div>
    </div>
  </div>
</template>
<script>
export default {

  methods: {
    goBack() {
      return this.$router.go(-1)
    }
  }
}
</script>

