<template>
    <h3>Parent</h3>
    <Child :title="msg" :age="age" :names="names" :obj="obj" />
</template>
<script>
import Child from './Child.vue'
export default {
    data() {
        return {
            msg: 'Parent数据1',
            age: 20,
            names: ['张三', '李四', '王五'],
            obj: {
                name: '张三',
                age: 20,
                address: '北京'
            }
        }
    },
    components: {
        Child
    }
}
</script>