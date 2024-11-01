<template>
    <p>我是子组件</p>
    <slot name="header" :childMsg="childMsg"></slot>
    <!-- <slot name="header"></slot> -->
</template>



<script>
export default {
    data() {
        return {
            childMsg: "我来自子组件"

        }
    },

}


</script>