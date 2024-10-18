<template>
    <h3>方法事件处理器</h3>
    <button @click="addCount">Add</button>
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
        addCount(e) {
            e.target.innerHTML = "Add" + this.count
            // 读取data里面的数据：this.count
            this.count++;
        }
    }

};


</script>