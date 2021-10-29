<template>
  <div class="w-full px-4 md:px-6 text-xl text-gray-800 leading-normal" style="font-family:Georgia,serif;">
    <nuxt-content :document="article" tag="article"/>

    <hr class="border-b-2 border-gray-400 mb-8 mx-4">

    <Newsletter/>

    <Author/>

    <hr class="border-b-2 border-gray-400 mb-8 mx-4">

    <Pagination/>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content(params.slug).fetch();

    return { article }
  }
}
</script>
