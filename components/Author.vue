<template>
  <div class="w-full px-2 xs:mb-6 xl:mb-12 article-card">
    <NuxtLink
      :to="`/blog/author/${author.name}`"
      class="rounded-xl flex transition-shadow duration-150 bg-blue-50 ease-in-out shadow-sm shadow-lg xxlmax:flex-col"
    >
      <figure class="xl:flex p-8 xl:p-0">
        <img
          class="w-32 h-32 xl:w-48 xl:h-auto xl:rounded-none rounded-full mx-auto object-cover"
          :src="author.img"
          alt=""
          width="384"
          height="512"
        />
        <div class="pt-6 xl:p-8 text-center xl:text-left space-y-4">
          <blockquote>
            <p class="text-lg font-semibold">
              “Talk is cheap, tell me a joke.”
            </p>
          </blockquote>
          <figcaption class="font-medium">
            <div class="text-cyan-600">{{ author.name }}</div>
            <div class="text-gray-500">{{ author.bio }}</div>
          </figcaption>
        </div>
      </figure>
    </NuxtLink>
  </div>
</template>

<script>
export default {
  props: {
    author: {
      type: Object,
      required: true
    }
  }
}
</script>
