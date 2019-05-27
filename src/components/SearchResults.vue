<template lang="html">
  <div class="search-results">
    <div v-bind:key="searchResult._id" v-for="searchResult in searchResults">
      <h3>{{ searchResult._source.title }}</h3>
      {{ searchResult.highlight.__ob__.value.text[0] }}
    </div>

  </div>
</template>

<script>
  export default {
    name: 'SearchResults',
    components: {
    },
    props:["searchResults"]
  }
</script>

<style lang="css">
</style>
