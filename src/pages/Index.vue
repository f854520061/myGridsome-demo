<template>
  <Layout>
    <div class="container">
      <div class="hero">
        <h1 class="hero-title">{{ general.title }}</h1>
        <h2 class="hero-subtitle">
          {{ general.desc }}
        </h2>
      </div>
      <div class="projects" data-v-50cbff3e="">
        <div
          v-for="item in $page.projectList.edges"
          :key="item.node.id"
          class="project"
          data-v-50cbff3e=""
        >
          <g-link
            :to="`/projects/${item.node.id}/`"
            class="project-link"
            data-v-50cbff3e=""
            ><img
              :alt="item.node.title"
              :src="`${GRIDSOME_API_URL + item.node.cover.url}`"
              class="thumbnail g-image g-image--lazy g-image--loaded"
              data-v-50cbff3e=""
            /><noscript data-v-50cbff3e=""
              ><img
                :src="`${GRIDSOME_API_URL + item.node.cover.url}`"
                class="thumbnail g-image g-image--loaded"
                :alt="item.node.title"
            /></noscript>
            <h3 class="project-title" data-v-50cbff3e="">
              {{ item.node.title }}
            </h3>
            <div class="categories" data-v-50cbff3e="">
              <span class="category" data-v-50cbff3e="">{{
                item.node.desc
              }}</span>
            </div>
          </g-link>
        </div>
      </div>
    </div>

    <div data-v-460714ac="">
      <div class="latest-journals-heading container" data-v-460714ac="">
        <span class="label" data-v-460714ac="">Latest and greatest</span>
      </div>
      <div class="latest-journals" data-v-460714ac="">
        <div class="container" data-v-460714ac="">
          <g-link
            v-for="item in $page.journals.edges"
            :key="item.node.id"
            :to="`/journals/${item.node.id}`"
            class="journal"
            data-v-460714ac=""
            ><h3 class="journal-title" data-v-460714ac="">
              {{ item.node.title }}
            </h3>
          </g-link>
        </div>
      </div>
    </div>
  </Layout>
</template>

<page-query>
query {
  projectList: allStrapiProjectList {
    edges {
      node {
        id
        title
        desc
        cover {
          url
        }
      }
    }
  }

  journals: allStrapiJournal {
    edges {
      node {
        id
        title
      }
    }
  }

  general: allStrapiGeneral {
    edges {
      node {
        title
        desc
      }
    }
  }
}
</page-query>

<script>
export default {
  name: "Home",
  computed: {
    general() {
      return this.$page.general.edges[0].node;
    },
  },
};
</script>

<style>
</style>
