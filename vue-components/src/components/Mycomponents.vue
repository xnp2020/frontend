<template>
    <p class="isActive">{{ msg }}</p>
</template>


<script>
export default {
    data() {
        return {
            msg: "Hello"
        }
    }
}

</script>

// scoped声明样式只在当前组件有效
<style scoped>
.isActive {
    color: red;
    font-size: 30px;
}
</style>