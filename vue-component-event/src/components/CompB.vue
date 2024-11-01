<template>
    <h3>CompB</h3>
    <p>{{ title }}</p>
    <p>{{ onEvent('我是子组件，我传递数据了') }}</p>
</template>


<script>
export default {
    data() {
        return {

        }
    },
    props: {
        title: {
            type: String,
            required: false
        },
        onEvent: {
            type: Function,
            required: false
        }
    },
}

</script>