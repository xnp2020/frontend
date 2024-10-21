<template>
    <div ref="myDiv" class="container">{{ content }}</div>
    <input type="text" ref="username">
    <button @click="getElementHandle">获取元素</button>

</template>

<script>
/**
 * 内容改变：{{ content }}
 * 属性改变：v-bind:content="content"
 * 事件改变：v-on:click="updateHandle"
 * 如果没有特别的需求，不要直接操作DOM
 */

export default {
    data() {
        return {
            content: "Hello Vue.js"

        };
    },
    methods: {
        getElementHandle() {
            this.$refs.myDiv.innerHTML = "哈哈哈";
            console.log(this.$refs.username.value);
        }
    }
}

</script>