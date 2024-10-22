<template>

    <button @click="clickEventHandle">子组件：点击传递Child数据到父组件</button>
</template>

<script>
export default {
    data() {
        return {
            msg: "Child中的数据"
        }
    },
    methods: {
        clickEventHandle() {
            // 触发父组件的事件
            this.$emit("child-click", this.msg);
        }
    }
}

</script>