<template>
  <div class="">
    <div class="border-b border-gray-200 py-10 flex items-center">
      <h4 class="text-xl font-bold">Onderwerpen</h4>
      <div class="flex flex-wrap ml-3">
        <a v-for="tag in tags" :key="tag" href="#" class="mr-3 py-1 px-3 rounded-full bg-green-400 text-white text-sm">
          {{ tag }}
        </a>
      </div>
    </div>
    <div class="pt-10">
      <h1 class="text-5xl font-black">New on the blog</h1>
      <ul class="mt-8 flex">
        <PostPreview v-for="post in posts" :key="post.slug" :post="post" />
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "index.vue",

  async asyncData({ $content }) {
    const posts = await $content({ deep: true })
      .only(['title', 'tags', 'slug', 'image', 'description', 'createdAt'])
      .sortBy('createdAt', 'desc')
      .where({ isArchived: false })
      .limit(25)
      .fetch();

    console.log(posts);

    return {
      posts
    }
  },

  data() {
    return {
      posts: [],
      tags: []
    }
  },

  created() {
    this.tags = this.uniqueTags();
  },

  methods: {
    uniqueTags() {
      const tags = this.posts.reduce((tags, post) => tags.concat(post.tags), []);
      return [...new Set(tags)];
    }
  }
}
</script>
