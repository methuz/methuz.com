<template>
  <ul
    class="w-100 flex md:flex-row flex-wrap justify-evenly items-center mr-2 leading-none font-mono"
  >
    <li class="flex-grow mr-3 lg:mr-4 mb-1 lg:mb-0 text-center">
      <NuxtLink
        to="/dataengineer"
        class="active--exact active lg:text-base hover:text-primary text-primary font-bold text-xl"
        ><span
          ><font style="vertical-align: inherit"
            ><font style="vertical-align: inherit">Data</font></font
          ></span
        ></NuxtLink
      >
    </li>
    <li class="flex-grow mr-3 lg:mr-4 mb-1 lg:mb-0 text-center">
      <NuxtLink
        to="/blockchain"
        class="active--exact active lg:text-base hover:text-primary text-primary font-bold text-xl"
        ><span
          ><font style="vertical-align: inherit"
            ><font style="vertical-align: inherit">Blockchain</font></font
          ></span
        ></NuxtLink
      >
    </li>
    <li class="flex-grow mr-3 lg:mr-4 mb-1 lg:mb-0 text-center">
      <NuxtLink
        to="/line"
        class="active--exact active lg:text-base hover:text-primary text-primary font-bold text-xl"
        ><span
          ><font style="vertical-align: inherit"
            ><font style="vertical-align: inherit">Bot</font></font
          ></span
        ></NuxtLink
      >
    </li>
  </ul>
</template>
