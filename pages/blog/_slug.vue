<template>
  <article
    class="flex lg:h-screen w-screen lg:overflow-hidden xs:flex-col lg:flex-row"
  >
    <div class="relative lg:w-1/2 xs:w-full xs:h-84 lg:h-full post-left">
      <img
        :src="article.img"
        :alt="article.alt"
        class="absolute h-full w-full object-cover"
      />
      <div class="overlay"></div>
      <div class="absolute top-32 right-32 text-white">
        <div class="mt-16 mb-3 flex uppercase text-sm">
          <p class="font-mono font-bold mr-3">
            {{ formatDate(article.updatedAt) }}
          </p>
          <span class="font-mono font-bold mr-3">•</span>
          <p>{{ article.author.name }}</p>
        </div>
        <!--<h1 class="text-6xl font-bold">{{ article.title }}</h1>-->
        <span v-for="(tag, id) in article.tags" :key="id">
          <NuxtLink :to="`/blog/tag/${tags[tag].slug}`">
            <span
              class="font-mono truncate uppercase tracking-wider font-medium text-sm px-2 py-1 rounded-full mr-2 mb-2 border border-light-border dark:border-dark-border transition-colors duration-300 ease-linear bg-opacity-70 bg-green-600"
            >
              {{ tags[tag].name }}
            </span>
          </NuxtLink>
        </span>
      </div>
    </div>
    <div
      class="relative xs:py-8 xs:px-8 lg:py-32 lg:px-16 lg:w-1/2 xs:w-full h-full overflow-y-scroll markdown-body post-right custom-scroll"
    >
      <h1 class="font-bold text-4xl">{{ article.title }}</h1>
      <p>{{ article.description }}</p>
      <p class="pb-4 italic">
        Post last updated: {{ formatDate(article.updatedAt) }}
      </p>
      <!-- content from markdown -->
      <nuxt-content :document="article" />
      <!-- content author component -->
      <author :author="article.author" />
      <!-- prevNext component -->
      <PrevNext :prev="prev" :next="next" class="mt-8" />
    </div>
  </article>
</template>
<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('articles', params.slug).fetch()
    const tagsList = await $content('tags')
      .only(['name', 'slug'])
      .where({ name: { $containsAny: article.tags } })
      .fetch()
    const tags = Object.assign({}, ...tagsList.map((s) => ({ [s.name]: s })))
    const [prev, next] = await $content('articles')
      .only(['title', 'slug'])
      .sortBy('createdAt', 'asc')
      .surround(params.slug)
      .fetch()
    return {
      article,
      tags,
      prev,
      next
    }
  },
  methods: {
    formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    }
  }
}
</script>
<style>
.nuxt-content p {
  margin-bottom: 20px;
}
.nuxt-content h2 {
  font-weight: bold;
  font-size: 28px;
}
.nuxt-content h3 {
  font-weight: bold;
  font-size: 22px;
}
.icon.icon-link {
  width: 20px;
  height: 20px;
  background-size: 20px 20px;
}
</style>
