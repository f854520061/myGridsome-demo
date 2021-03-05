<template>
  <Layout>
    <div class="journal" data-v-2a0eef53="">
      <div class="container journal-container" data-v-2a0eef53="">
        <div class="journal-header" data-v-2a0eef53="">
          <h1 class="journal-title" data-v-2a0eef53="">
            {{ journal.title }}
          </h1>
          <!-- <div class="journal-meta" data-v-2a0eef53="">
            <div class="journal-author" data-v-2a0eef53="">
              <span class="label" data-v-2a0eef53="">Author</span
              ><span class="author-name" data-v-2a0eef53=""
                >Nichlas W. Andersen</span
              >
            </div>
            <div class="journal-date" data-v-2a0eef53="">
              <span class="label" data-v-2a0eef53="">Date</span>
              <div data-v-2a0eef53="">18. May 2019</div>
            </div>
            <div class="journal-time" data-v-2a0eef53="">
              <span class="label" data-v-2a0eef53="">Time</span
              ><span data-v-2a0eef53="">1 min read</span>
            </div>
          </div> -->
        </div>
        <div class="journal-content" data-v-2a0eef53="">
          {{ journal.content }}
        </div>
      </div>
    </div>
  </Layout>
</template>

<page-query>
query ($id: ID!) {
  journal: strapiJournal (id: $id) {
    title
    content
  }
}
</page-query>

<script>
export default {
  name: "JournalPage",
  computed: {
    journal () {
      return this.$page.journal
    }
  }
};
</script>

<style>
</style>