<template>
    <p :style="{ color: activeColor, fontSize: fontSize }">Style绑定1</p>
    <p :style=styleObject>Style绑定2</p>
    <p :style="[styleObject]">Style绑定3</p>

</template>

<script>
export default {
    data() {
        return {
            activeColor: 'green',
            fontSize: '30px',
            styleObject: {
                color: 'green',
                fontSize: '30px'
            }
        };
    }
};

</script>