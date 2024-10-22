<template>
    <h3>Parent</h3>
    <ComponentB :title="title" :age="age" :names="names" :obj="obj" />

</template>

<script>
import ComponentB from './ComponentB.vue'
export default {
    data() {
        return {
            title: "标题1",
            age: 20,
            names: ['张三', '李四', '王五'],
            obj: {
                "name": "张三",
                "age": 20,
                "address": "北京"
            }
        };
    },
    components: {
        ComponentB
    }
}
</script>