<template>
    <div class="main">
        <h3>Main</h3>
        <Article />
        <Article />
    </div>
</template>




<script>
import Article from './Article.vue';

export default {
    components: {
        Article
    }
}

</script>




<style scoped>
.main {
    float: left;
    width: 70%;
    height: 600px;
    border: 5px solid gray;
    box-sizing: border-box;

}
</style>