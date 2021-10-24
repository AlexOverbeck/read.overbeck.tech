<template>
  <div>
    <h1>Articles</h1>

    <div v-if="loading">
      Loading...
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      loading: false,
      articles: []
    }
  }
}
</script>