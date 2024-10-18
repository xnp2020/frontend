<template>
    <h3>event传递参数，获取event对象</h3>
    <p @click="getNameHandler(item, $event)" v-for="(item, index) of names" :key="index">{{ item }}</p>
</template>

<script>
export default {
    data() {
        return {
            names: ["a", "b", "c"]

        };
    },
    methods: {
        getNameHandler(name, e) {
            console.log(name);
            console.log(e);
        }
    }

};


</script>