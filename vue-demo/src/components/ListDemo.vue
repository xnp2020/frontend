<template>
    <h3>列表渲染</h3>
    <p v-for="(name, index ) in names">{{ name }}:{{ index }}</p>
    <div v-for="item of result">
        <p>{{ item.title }}</p>
        <img :src="item.avatar" alt="">
    </div>
    <div>
        <p v-for="value, key, index of userInfo">{{ index }}-{{ key }}-{{ value }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            names: ['John', 'Jim', 'Joe'],
            result: [
                {
                    "id": 1,
                    "title": "title1",
                    "avatar": "http://www.baidu.com"
                },
                {
                    "id": 2,
                    "title": "title2",
                    "avatar": "http://www.baidu2.com"
                },
                {
                    "id": 3,
                    "title": "title3",
                    "avatar": "http://www.baidu3.com"
                },
            ],
            userInfo: {
                name: 'John',
                age: 18,
                sex: '男'
            }
        }
    }
}

</script>
