<template>
    <h3>事件修饰符</h3>
    <a @click.prevent="clickHandle" href="https://cn.vuejs.org/v2/guide/events.html#事件修饰符">柏芝</a>
    <div @click="clickDiv">
        <p @click.stop="clickP">测试冒泡</p>
    </div>
</template>

<script>
export default {
    data() {
        return {


        };
    },
    methods: {
        clickHandle(e) {
            // 阻止默认事件
            // e.preventDefault();
            console.log("点击了");
            // 阻止事件冒泡
            e.stopPropagation();
        },
        clickDiv() {

            console.log("点击了div");
        },
        clickP() {
            //e.stopPropagation();
            console.log("点击了p");
        }
    }
}


</script>