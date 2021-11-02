<template>
  <div class="flex w-full items-center font-sans px-4 py-12">
    <img alt="Avatar of Author" class="w-10 h-10 rounded-full mr-4" src="http://i.pravatar.cc/300">
    <div class="flex-1 px-2">
      <p class="text-base font-bold text-base md:text-xl leading-none mb-2">
        {{ author }}
      </p>
      <p class="text-gray-600 text-xs md:text-base">
        Laatst geüpdatet op: {{ formattedDate(updatedAt) }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    author: {
      type: String,
      required: true
    },
    updatedAt: {
      type: Date,
    }
  },
  name: "Author",
  methods: {
    formattedDate(date) {
      const options = {
        weekday: 'long',
        year: 'numeric',
        month: 'long',
        day: 'numeric'
      }

      return new Intl.DateTimeFormat('nl-NL', options).format(date);
    }
  }
}
</script>

<style scoped>

</style>
