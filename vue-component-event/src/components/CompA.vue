<template>
    <h3>CompA</h3>
    <p>父元素：{{ message }}</p>
    <CompB :title="title" :onEvent="dataFn" />
</template>


<script>
import CompB from './CompB.vue';

export default {
    data() {
        return {
            title: "标题",
            message: ""
        }
    },
    components: {
        CompB
    },
    methods: {
        dataFn(data) {
            // console.log(data);
            this.message = data;
        }
    }
}

</script>