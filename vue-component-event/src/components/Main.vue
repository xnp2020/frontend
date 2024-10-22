<template>
    <h3>Main</h3>
    <p>搜索内容为：{{ search }}</p>
    <SearchComponent @search-change="getSearch" />
</template>


<script>
import SearchComponent from './SearchComponent.vue';

export default {
    components: {
        SearchComponent
    },
    data() {
        return {
            search: "abc"
        }
    },
    methods: {
        getSearch(data) {
            this.search = data;
        }
    }

}

</script>