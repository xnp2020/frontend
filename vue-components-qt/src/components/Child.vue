<template>
    <h3>Child</h3>
    <p>{{ title }}</p>
    <p>{{ age }}</p>
    <ul>
        <li v-for="(item, index) in names" :key="index">{{ item }}</li>
    </ul>

    <p>{{ obj.name }}</p>
    <p>{{ obj.age }}</p>
    <p>{{ obj.address }}</p>

</template>
<script>
export default {
    data() {
        return {


        }
    },

    // props传递数据只能从父组件向子组件传递
    // props能传递任意类型

    props: ["title", "age", "names", 'obj']
}
</script>