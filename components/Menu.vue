<template>
  <ul
    class="w-100 flex md:flex-row flex-wrap justify-evenly items-center mr-2 leading-none font-mono"
  >
    <li class="flex-grow mr-3 lg:mr-4 mb-1 lg:mb-0 text-center">
      <NuxtLink
        to="/blog/tag/data"
        class="active--exact active hover:text-primary text-primary font-bold text-xl"
        ><span> Data </span></NuxtLink
      >
    </li>
    <li class="flex-grow mr-3 lg:mr-4 mb-1 lg:mb-0 text-center">
      <NuxtLink
        to="/blog/tag/blockchain"
        class="active--exact active hover:text-primary text-primary font-bold text-xl"
        ><span>Blockchain</span></NuxtLink
      >
    </li>
    <li class="flex-grow mr-3 lg:mr-4 mb-1 lg:mb-0 text-center">
      <NuxtLink
        to="/blog/tag/bot"
        class="active--exact active hover:text-primary text-primary font-bold text-xl"
        ><span>Bot</span></NuxtLink
      >
    </li>
  </ul>
</template>
