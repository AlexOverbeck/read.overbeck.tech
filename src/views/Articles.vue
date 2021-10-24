<template>
  <div>
    <h1>Articles</h1>
    <div v-for="article in articles" :key="article.id">
      <h2>{{ article.title }}</h2>
      <p>{{ article.summary }}</p>
      <a :href="article.url">{{ article.url }}</a>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      articles: []
    }
  },
  created () {
    this.fetchArticles();
  },
  methods: {
    async fetchArticles () {
      const response = await fetch('https://api.overbeck.tech/articles');

      if (response.ok) {
        this.articles = await response.json();
      }
    }
  }
}
</script>