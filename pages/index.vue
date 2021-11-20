<template>
  <!-- <Tutorial/> -->
  <article>
    1. This header is from /components/cpnt200_header.vue
    <cpnt-200-header />
    <br />
    2. This is the link to the second page.<br />
    <NuxtLink to="/second">To Second page</NuxtLink>
    <br />
    <br />
    3. This is from /content/home.md using the nuxt-content tag.
    <nuxt-content :document="page" />
    <br />
    4. This image optimized by the sizes attribute is from /static folder using the nuxt-img tag.
    <nuxt-img 
        src="/pexels-richard-verbeek-572861.jpg" 
        sizes="sm:100vw md:50vw lg:400px"/>
    
  </article>
</template>
<style scoped>
a {
  color:blue;
  text-decoration:underline;
}
.nuxt-content-container, .nuxt-content {
  color:green;
}
</style>
<script>
import cpnt200_header from '../components/cpnt200_header.vue'
export default {
  components: { cpnt200_header },
  async asyncData ({ $content }) {
    const page = await $content('home').fetch()
    return {
      page
    }
  }
}
</script>
