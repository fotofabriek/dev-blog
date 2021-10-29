<template>
  <div class="font-sans flex justify-between content-center px-4 pb-12">
    <div class="text-left">
      <span class="text-xs md:text-sm font-normal text-gray-600">&lt; Previous Post</span><br>
      <p>
        <a class="break-normal text-base md:text-sm text-green-500 font-bold no-underline hover:underline"
           href="#">Blog title
        </a>
      </p>
    </div>
    <div class="text-right">
      <span class="text-xs md:text-sm font-normal text-gray-600">Next Post &gt;</span><br>
      <p>
        <a class="break-normal text-base md:text-sm text-green-500 font-bold no-underline hover:underline"
           href="#">
          Blog title
        </a>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Pagination"
}
</script>

<style scoped>

</style>
