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
    <br />
    5. This is a post for blog.
    <article>
      <h1>{{ blog.title }}</h1>
      <nuxt-content :document="blog" />
    </article>
    <br />
    6. This is a profile posted a porfile collection.
    <article>
      <h1>{{ profile.name }}</h1>
      <h1>{{ profile.dateofbirth }}</h1>
      <img src="{{profile.picture}}">
      <h1>{{ profile.introduction }}</h1>
      <h1>{{ profile.information}}</h1>
      
    </article>
    <br />
    7. This is a code snippet posted a code snippet collection.
    <nuxt-content :document="code" />

  </article>
</template>
<style scoped>
a {
  color:blue;
  text-decoration:underline;
}

</style>
<script>
import cpnt200_header from '../components/cpnt200_header.vue'
export default {

  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    };
  },
  components: { cpnt200_header },
  async asyncData ({ $content }) {
    const page = await $content('home').fetch()
    const blog = await $content('blog/2021-11-21-this-is-a-test-post').fetch()
    const profile = await $content('profile/2021-11-21-this-is-my-profile').fetch()
    const code = await $content('code-snippet/2021-11-21-this-is-a-code-snippet-from-the-conig-yml').fetch()
    return {
      page, blog, profile, code
    }
  }
}
</script>
