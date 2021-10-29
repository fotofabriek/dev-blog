<template>
  <nav id="header" class="w-full z-10 top-0 bg-white shadow sticky">

    <div class="w-full md:max-w-5xl mx-auto flex flex-wrap items-center justify-between mt-0 py-3">

      <a class="text-gray-900 no-underline hover:no-underline font-extrabold text-xl" href="/">
        Studentenblogwerk
      </a>

      <div class="block lg:hidden pr-4">
        <button id="nav-toggle"
                class="flex items-center px-3 py-2 border rounded text-gray-500 border-gray-600 hover:text-gray-900 hover:border-green-500 appearance-none focus:outline-none">
          <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/>
          </svg>
        </button>
      </div>

      <div
        id="nav-content"
        class="w-full flex-grow lg:flex lg:items-center lg:w-auto hidden lg:block mt-2 lg:mt-0 bg-gray-100 md:bg-transparent z-20">
        <ul class="list-reset lg:flex justify-end flex-1 items-center">
          <li class="mr-3">
            <a class="inline-block py-2 px-4 text-gray-900 font-bold no-underline" href="#">Active</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Header"
}
</script>
