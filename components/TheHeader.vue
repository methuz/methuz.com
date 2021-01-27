<template>
  <header class="flex flex-col items-stretch lg:flex-row mb-3 lg:mb-6 pl-2">
    <NuxtLink class="flex flex-col mb-2 lg:mb-0 lg:flex-row items-center" to="/"
      ><Logo class="lg:mr-3 mb-1 lg:mb-0" />
      <p
        class="text-base text-blue-500 leading-tight font-mono font-bold hover:text-primary active"
      >
        @Methuz
      </p>
    </NuxtLink>
    <AppSearchInput class="place-self-center md:ml-4 mb-3 lg:mb-0" />
    <Menu class="ml-4 mb-3 lg:mb-0" />
  </header>
</template>
