<template>
  <li class="transition-all duration-500 ease-in-out mr-5 max-w-xs">
    <a :href="`${post.path}`" class="flex flex-col">
      <nuxt-img
        class="rounded-lg object-cover"
        :src="post.image"
        preset="preview"
        width="350"
        height="250"
      />
      <div class="py-5">
        <h2 class="text-xl font-semibold">{{ post.title }}</h2>
        <p class="my-2 text-gray-400">{{ post.description }}</p>
        <ul v-if="post.tags" class="flex flex-wrap mt-2">
            <li class="text-white mr-2 text-sm py-1 px-2 rounded-full bg-green-400 mb-2" v-for="tag in post.tags" :key="tag">
            {{ tag }}
            </li>
        </ul>
      </div>
    </a>
  </li>
</template>

<script>
export default {
  props: {
    post: {
        type: Object
    },
  }
}
</script>