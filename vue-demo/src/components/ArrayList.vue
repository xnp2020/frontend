<template>
    <h3>数组变化侦听</h3>
    <button @click="addListHandle">push添加数组</button>
    <ul>
        <li v-for="(name, index) in names" :key="index">{{ name }}</li>
    </ul>

    <h3>数组1</h3>
    <ul>
        <li v-for="(item, index) in num1" :key="index">{{ item }}</li>
    </ul>


    <!-- <h3>数组2</h3>
    <ul>
        <li v-for="(item, index) in num2" :key="index">{{ item }}</li>
    </ul> -->

    <button @click="concatHandle">concat添加数组</button>



</template>

<script>
export default {
    data() {
        return {
            names: ["a", "b", "c"],
            num1: [1, 2, 3],
            num2: [4, 5, 6]

        };
    },
    methods: {
        addListHandle() {
            this.names.push("d"); //引起UI自动更新
            // this.names.concat(["d"]) //不引起UI自动更新，需要重新赋值 this.names = this.names.concat(["d"])
        },
        concatHandle() {
            this.num1 = this.num1.concat(this.num2)
        }
    }
}

</script>