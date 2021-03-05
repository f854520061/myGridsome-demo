<template>
  <Layout>
    <div data-v-7f3c42a8="" class="project">
      <div data-v-7f3c42a8="" class="container">
        <div data-v-7f3c42a8="" class="project-header">
          <h1 data-v-7f3c42a8="" class="project-title">{{ $page.project.title }}</h1>
          <!-- <div data-v-7f3c42a8="" class="project-info">
            <div data-v-7f3c42a8="" class="categories-container">
              <div data-v-7f3c42a8="" class="categories">
                <span data-v-7f3c42a8="" class="label">Categories</span
                ><span data-v-7f3c42a8="" class="category">photography</span
                ><span data-v-7f3c42a8="" class="category">pink</span>
              </div>
            </div>
            <div data-v-7f3c42a8="" class="year-container">
              <span data-v-7f3c42a8="" class="label">Year</span>
              <div data-v-7f3c42a8="">2019</div>
            </div>
          </div> -->
        </div>
        <div data-v-7f3c42a8="" class="content">
          <p>
            {{ $page.project.content }}
          </p>
          <p>
            <img
              class="g-image g-image--lazy g-image--loaded"
              :src="`${ GRIDSOME_API_URL + $page.project.cover.url }`"
              width="2560"
              sizes="(max-width: 2560px) 100vw, 2560px"
            /><noscript
              ><img
                class="g-image g-image--lazy g-image--loaded"
                :src="`${ GRIDSOME_API_URL + $page.project.cover.url }`"
                width="2560"
            /></noscript>
          </p>
        </div>
      </div>
    </div>
  </Layout>
</template>

<page-query>
query ($id: ID!) {
  project: strapiProjectList (id: $id) {
    cover {
      url
    }
    content
    title
  }
}
</page-query>

<script>
export default {
    name: 'ProjectsPage'
}
</script>

<style>
</style>