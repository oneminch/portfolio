<template>
  <section class="w-full">
    <article
      class="w-full prose dark:prose-invert prose-img:rounded-xl lg:prose-base prose-slate mx-auto text-slate-800 dark:text-slate-100 font-serif"
    >
      <!-- Breadcrumb nav menu -->
      <nav class="flex items-center mb-6 py-2 px-4 text-lg [&>*]:mr-4">
        <NuxtLink
          class="breadcrumb-nav-item focused-link dark:text-slate-200 hover:before:visible before:invisible relative -z-0 no-underline"
          to="/"
          >Home</NuxtLink
        >
        <Icon name="octicon:chevron-right-16" />
        <NuxtLink
          class="breadcrumb-nav-item focused-link dark:text-slate-200 hover:before:visible before:invisible relative -z-0 no-underline"
          to="/blog"
          >Blog</NuxtLink
        >
      </nav>
      <!-- Blog Post -->
      <ContentDoc v-slot="{ doc }">
        <h1>{{ doc.title }}</h1>
        <ContentRenderer :value="doc" />
      </ContentDoc>
    </article>
  </section>
</template>

<script setup></script>

<style scoped>
  article > div a {
    @apply text-green-500 !important;
  }

  .breadcrumb-nav-item::before {
    @apply content-[''] absolute origin-center w-full h-full scale-x-150 scale-y-125 rounded-md -z-10 bg-gradient-to-r from-green-200 to-yellow-200 dark:from-transparent dark:to-transparent dark:bg-slate-700;
  }
</style>