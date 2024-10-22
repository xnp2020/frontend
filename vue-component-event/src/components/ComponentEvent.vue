<template>
    <h3>父组件：组件事件</h3>
    <Child @child-click="getHandle" />
    <p>父组件中接受到子组件的数据：{{ message }}</p>
</template>

<script>
import Child from '../components/Child.vue';

export default {
    components: {
        Child
    },
    data() {
        return {
            message: ""
        }
    },
    methods: {
        getHandle(data) {
            //console.log("子组件触发了父组件的事件", data);
            this.message = data;
        }
    }
}
</script>