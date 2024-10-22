<template>
    <input type="text" v-model="search">
</template>



<script>
export default {
    data() {
        return {
            search: ""
        }
    },
    watch: {
        search(newValue, oldValue) {
            // 触发父组件的事件
            this.$emit("search-change", newValue);
        }
    }
}


</script>