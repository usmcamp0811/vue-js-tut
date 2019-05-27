<template>
    <div>
        <form @submit="searchQuery">
            <input type="text" v-model="query" name="query" placeholder="Add Todo..." />
            <input type="submit" value="Submit" class="btn" />
        </form>
    </div>
</template>

<script>


export default {
    name: "SearchBox",
    data() {
        return {
            query: ''
        }
    },
    methods: {
        searchQuery(e) {
            // keeps js from trying to submit to file and refresh page
            e.preventDefault();
            const newQuery = {
                query: this.query
            }
            // Send up to parent
            this.$emit('new-query', newQuery);
            this.query = '';
        }
    }
}
</script>

<style lang="css">

</style>
