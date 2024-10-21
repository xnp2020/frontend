<template>
    <div>
        <h2>输入一个数字：</h2>
        <input v-model.number="userInput" />
        <p>你输入的数字是：{{ userInput }}</p>
        <button @click="doubleNumber">双倍数字</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            userInput: 0,
        };
    },
    methods: {
        doubleNumber() {
            this.userInput *= 2;
        },
    },
};
</script>