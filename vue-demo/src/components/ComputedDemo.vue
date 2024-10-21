<template>
    <h3>{{ itbaizhan.msg }}</h3>
    <p>{{ getLength }}</p>
    <p>{{ getLengths() }}</p>

</template>

<script>
export default {
    data() {
        return {
            itbaizhan: {
                msg: "我是computed计算属性",
                content: ["a", "b"]
            }

        }
    },
    computed: {
        // 计算属性的getter
        // 计算属性的值会根据它的依赖自动缓存起来，所以多次访问同一个计算属性会直接返回缓存结果，而不会重复执行 getter 函数。
        // 只有当它的相关值发生了改变，缓存的计算属性才会重新求值。
        getLength() {
            return this.itbaizhan.content.length > 0 ? 'Yes' : 'No';
        }
    },
    methods: {
        getLengths() {
            return this.itbaizhan.content.length > 0 ? 'Yes' : 'No';
        }

    }
}

</script>