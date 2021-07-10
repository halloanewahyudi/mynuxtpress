<template>
  <div>
    <b-navbar toggleable="sm" type="light" variant="light">
      <div class="container">
      <b-navbar-toggle target="nav-text-collapse"></b-navbar-toggle>
      <b-navbar-brand>ane Wahyudi</b-navbar-brand>

      <b-collapse id="nav-text-collapse" is-nav>
         <b-navbar-nav class="ml-auto">
             <nuxt-link to="/" class="nav-link">Home</nuxt-link>
              <nuxt-link to="/about" class="nav-link">About</nuxt-link>
             <nuxt-link to="/blog" class="nav-link">Blog</nuxt-link>
         </b-navbar-nav>
      </b-collapse>
      </div>
    </b-navbar>
  </div>
</template>