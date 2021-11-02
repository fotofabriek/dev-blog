<template>
  <div class="w-full px-4 md:px-6 text-xl text-gray-800 leading-normal">
    <NuxtContent 
      class="prose prose-sm sm:prose lg:prose-lg xl:prose-2xl content"
      :document="article" />

    <hr class="border-b-2 border-gray-400 my-8">

    <Newsletter/>

    <Author v-if="article.author" :author="article.author" :updatedAt="article.updatedAt" />

    <hr class="border-b-2 border-gray-400 mb-8">

    <Pagination/>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {

    const [ article ] = await $content({ deep: true })
      .where({ path: params.slug })
      .limit(1)
      .fetch();

    const [ prev, next ] = await $content({ deep: true })
      .only(['title', 'slug'])
      .sortBy('createdAt', 'asc')
      .surround(params.slug)
      .fetch()

    return { 
      article,
      prev,
      next
    }
  }
}
</script>

<style>
  .content {
    max-width: 100%!important;
  }
</style>
