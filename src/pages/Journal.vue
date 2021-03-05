<template>
  <Layout>
    <div data-v-da896d1e="" class="container">
      <div data-v-da896d1e="" class="journal-hero">
        <h1 data-v-da896d1e="" class="journal-header">
          a wise person once said...
        </h1>
      </div>
    </div>
    <g-link
      v-for="item in $page.journals.edges"
      :key="item.node.id"
      data-v-da896d1e=""
      :to="`/journals/${item.node.id}`"
      class="journal-post"
      ><div data-v-da896d1e="" class="container journal">
        <h2 data-v-da896d1e="" class="journal-title">
          {{ item.node.title }}
        </h2>
        <p data-v-da896d1e="" class="journal-excerpt">
          {{ item.node.desc }}
        </p>
      </div>
    </g-link>
  </Layout>
</template>

<page-query>
query {
  journals: allStrapiJournal {
    edges {
      node {
        id
        title
        desc
      }
    }
  }
}
</page-query>

<script>
export default {
  name: "Journal",
};
</script>

<style>
</style>