<template>
    <label for="1">子组件中搜索：</label>
    <input type="text" v-model="search" id="1">
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