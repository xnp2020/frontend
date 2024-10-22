<template>
    <p :class="{ 'active': isActive, 'text-danger': hasError }">Class样式绑定1</p>
    <p :class="classObject">Class样式绑定2</p>
    <p :class="[activeClass, errorClass]">Class样式绑定3</p>
    <p :class="[isActive ? 'active' : '']">Class样式绑定4</p>
    <p :class="[isActive ? 'active' : '', { 'text-danger': hasError }]">Class样式绑定5</p>

</template>

<script>
export default {
    data() {
        return {
            isActive: true,
            hasError: true,
            classObject: {
                'active': true,
                'text-danger': true
            },
            activeClass: 'active',
            errorClass: 'text-danger'
        }
    }
}


</script>

<style>
.text-danger {
    color: red;
}

.active {
    font-size: 30px;
}
</style>