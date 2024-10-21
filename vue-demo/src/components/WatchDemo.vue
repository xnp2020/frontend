<template>
    <h3>侦听器</h3>
    <p>{{ msg }}</p>
    <button @click="updateHandle">修改msg</button>
</template>

<script>
export default {
    data() {
        return {
            msg: "Hello"
        };
    },
    methods: {
        updateHandle() {
            this.msg = "Hello World";
        }
    },
    watch: {
        msg(newValue, oldValue) {
            console.log("newValue:", newValue);
            console.log("oldValue:", oldValue);
        }
    }
};

</script>