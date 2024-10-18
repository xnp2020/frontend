<template>
    <h3>event传递参数</h3>
    <button @click="addCount('hello')">Add</button>
    <p>{{ count }}</p>
</template>

<script>
export default {
    data() {
        return {
            count: 0
        };
    },
    methods: {
        addCount(msg) {
            console.log(msg);
            // 读取data里面的数据：this.count
            this.count++;
        }
    }

};


</script>