<template>
    <h3>child</h3>
    <p>{{ title }}</p>
    <p>{{ age }}</p>
    <ul>
        <li v-for="(item, index) in names" :key="index">{{ item }}</li>
    </ul>

    <p>{{ obj.name }}</p>
    <p>{{ obj.age }}</p>
    <p>{{ obj.address }}</p>

    <button @click="btnClick">按钮</button>
</template>

<script>
export default {
    props: {
        title: {
            type: [String, Number, Array],
            required: true
        },
        age: {
            type: Number,
            required: true,
            default: 18
        },

        // 数字和字符串可以直接default，但是数组和对象，必须通过工厂函数返回默认值
        names: {
            type: Array,
            default() {
                return ["空"];
            }
        },
        obj: {
            type: Object
        }

    },
    methods: {
        btnClick() {
            // props是只读的，不能修改
            console.log(this.title = "标题1");
        }
    }
}

</script>